# 工序 3 — 构图精修 (Composition + Retouch)

**目标**：在锁定主体的前提下，**一次性**完成两件事——① 把任意比例原图安全转换为目标明信片比例（默认 2:3 竖版），保证主体关键部分 100% 不被裁掉；② 在构图锁定图上做高清放大、去干扰、降噪、校正，产出一张干净、构图正确、清晰的底图，供 `art-transform` 重绘。

**为什么合并**：原 `composition-engine` 与 `retouch` 是紧邻的两步，且都工作在「同一张构图锁定底图」上——比例转换必须先于精修，精修又必须避开已锁定的主体区域。合并为一道工序可避免中间产物来回传递、减少一次 ImageGen 决策，逻辑更连贯。

**输入**：
- `subject-lock` 说明（含 `primary_subject`、`subject_bbox` 安全区、`crop_suggestion`、`remove_elements`）
- 原图
- `analyzer` 报告（含 `defects`，如 `low_resolution`）

**目标规格**：
- 默认比例 2:3 竖版（明信片）；用户指定其他比例（方形、横版）以用户为准
- 此工序输出的「构图锁定底图」用于后续 `art-transform` 重绘；重绘后短边封顶 1024px（ImageGen 限制）。若需实体印刷（≥1600px 短边），须在 `art-transform` 之后、进入 `post` 之前对重绘底图做 2× 超分。

## 3.1 构图引擎（比例安全转换）

**决策流程**：

1. 读取原图尺寸 `(W, H)` 与目标宽高比 `target_ar`（如 2:3 → 0.667）。
2. 取 `subject_bbox = (x1, y1, x2, y2)`：**原图坐标**下主体的包围盒，必须包含关键部分（顶部/头/尖顶）。
3. **计算安全裁切窗口**：
   - 以 `subject_bbox` 为中心、偏下对齐，按 `target_ar` 求出能完整包住主体 bbox 的最小裁切矩形。
   - 若该窗口完全落在原图内 → **策略 A：安全裁切**（零成本、无损）。
4. **若安全裁切窗口超出原图**（主体太大/太靠边，或横图转竖图时主体两侧缺背景）→ **策略 B：扩图（outpaint）**：
   - 用 ImageGen 图生图，提示词强制「seamlessly extend the [left/right/top] background only, keep the subject exactly as-is, no distortion, clean sky/ground, no new objects」，生成扩展后的图。
   - 在扩展图上重新计算安全裁切窗口 → 裁切到目标比例。
5. **极端兜底**：扩图后仍无法满足时，回退到「主体完整优先于比例」——保留主体完整，输出最接近目标的合法比例，并在 qc 阶段标注差异。

**工具映射**：
- 安全裁切：Pillow（`Image.crop`，纯几何，无损）
- 扩图：ImageGen 图生图（`input_fidelity` 高以保留主体；提示词强制只延展背景、主体不变）

## 3.2 精修（在构图锁定图上）

1. **放大**：若 analyzer 标记 `low_resolution`，用 ImageGen 图生图做 2x–4x 超分，保持细节不糊、不出现伪影。
2. **清理**：去除 `subject-lock` 中的 `remove_elements`（路人、杂物、电线、水印、反光）；主动避开 `subject_bbox` 主体区域。
3. **校正**：本阶段**不再做比例裁切**（已由 3.1 完成）。仅做水平 / 透视校正。
4. **降噪 / 锐化**：压制噪点、适度提升锐度，但**不过度**（避免塑料感、边缘描边感）。

**ImageGen 图生图提示参考**：
- 中文：「4K 超清，移除干扰物体，干净构图，保留主体，无伪影，细节丰富」
- 英文：`4K, ultra-detailed, remove distracting objects, clean composition, preserve the subject, no artifacts, enhanced sharpness`

## 输出

| 字段 | 说明 |
| --- | --- |
| `compretouched.png` | 已裁切/已扩图、比例正确、干净清晰的底图，供 `art-transform` 使用 |
| `safety_zone` | 主体在**构图锁定图坐标**下的 bbox（供 `art-transform` 保护主体、`post` 排版参考） |
| `decision` | 比例转换 A（安全裁切）/ B（扩图）/ fallback，及理由 |
| `composition_note` | 主体位置（居中偏下 / 左三分）、留白分布，供后续排版 |

## 与相邻工序关系

- 上游 `subject-lock`：仅提供主体与位置，本工序负责比例落地与清洁。
- 下游 `art-transform`：在 `compretouched.png` 上做绘画媒介重绘；须保护 `safety_zone` 内主体。

## 质量门禁

- 主体关键部分 100% 在画面内，无切顶、无切头、无切边。
- 裁切后主体占比符合 `subject-lock` 要求（≥40%），构图美观。
- 扩图接缝自然，无重复纹理、无畸变、无新物体。
- 主体清晰、无损伤、无畸变；去除物不留明显痕迹、无水印残留；无新增伪影或塑料感。
- 不达标 → 重做本工序，绝不带着问题进 `art-transform`。
