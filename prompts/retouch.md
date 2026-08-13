# 工序 3 — 高清 / 清理 (Retouch)

**目标**：在锁定主体的前提下，提升清晰度、清理干扰、修正基础瑕疵，产出一张干净底图。

**输入**：subject-lock 说明 + composition-engine 输出的 `composition_locked.png`。

**输出**：一张干净、清晰、构图正确的底图，供调色使用。

**步骤**：

1. **放大**：若 analyzer 标记 `low_resolution`，用 ImageGen 图生图做 2x–4x 超分，保持细节不糊、不出现伪影。
2. **清理**：去除 subject-lock 中的 `remove_elements`（路人、杂物、电线、水印、反光）。
3. **校正**：本工序**不再做比例裁切**（已由 composition-engine 在 `composition_locked.png` 完成）。仅做水平 / 透视校正；清理时主动避开 `safety_zone` 主体区域。
4. **降噪 / 锐化**：压制噪点、适度提升锐度，但**不过度**（避免塑料感、边缘描边感）。
5. 输出底图，进入 `color.md`。

**ImageGen 图生图提示参考**：

- 中文：「4K 超清，移除干扰物体，干净构图，保留主体，无伪影，细节丰富」
- 英文：`4K, ultra-detailed, remove distracting objects, clean composition, preserve the subject, no artifacts, enhanced sharpness`

**质量门禁**：

- 主体清晰、无损伤、无畸变。
- 去除物不留明显痕迹、无水印残留。
- 无新增伪影或塑料感。
- 不达标 → 重做本工序，绝不带着问题进 color。
