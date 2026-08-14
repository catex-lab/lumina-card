# 工序 4 — 艺术变换 (Art Transform)

**目标**：把 `compretouch` 产出的照片底图，重绘为选定的**绘画媒介风格**，让明信片从「照片」升级为「画作」。这是风格化的核心关卡，独立于构图与精修。

**输入**：`compretouch` 产出的 `compretouched.png`（构图正确、干净清晰）+ 用户选定的媒介。

## 可选媒介（7 种）

| key | 名称 | 视觉特征 |
| --- | --- | --- |
| `oil` | 油画 | 厚重笔触、明显肌理、饱和油润、光影塑造强 |
| `watercolor` | 水彩 | 通透晕染、湿边、留白、轻盈治愈 |
| `watercolor-silhouette` | 水彩剪影 | 靛蓝水彩剪影、极度留白、粗纹水彩纸、通透轻盈 |
| `ink` | 水墨剪影（中式） | 墨色剪影、极度留白、粗纹水彩纸、气韵生动 |
| `sketch` | 素描 | 单色线条/排线、铅笔或炭笔质感、结构清晰 |
| `illustration` | 插画 | 扁平/矢量/有限色、干净边缘、当代编辑感 |
| `vintage` | 复古 | 褪色暖黄、颗粒、暗角、怀旧胶片感 |

## 用户选择规则（务必遵守）

1. 用户在请求里**直接指定媒介**（如「用水彩风」「来张油画感的」）→ 直接用。
2. 用户**未指定**但 `subject-lock` / `analyzer` 已暗示合适媒介（如古建→`ink`、宠物→`illustration`）→ 可推荐并在确认节点提出，不擅自定死。
3. 用户完全没提且无明显暗示 → **主动询问一次**：「想要哪种艺术风格？油画 / 水彩 / 水彩剪影 / 水墨剪影 / 素描 / 插画 / 复古（默认水彩）」，给建议不编造。
4. **回退值**：用户未选且无偏好时，默认 `watercolor`（最通用、最不易翻车）。

## 步骤

1. 读取 `compretouched.png` 与 `safety_zone`（主体区域）。
2. 用 ImageGen 图生图按选定媒介重绘：
   - **保护主体**：提示词强制「preserve the exact subject, its identity, pose and key features; only change the rendering medium」，避免把人/地标/宠物画变形。
   - **媒介专属提示词**（见下）。
3. 输出重绘图，进入 `color.md`。

## 各媒介 ImageGen 提示词参考

- **oil（油画）**：`turn into an oil painting, visible bold brushstrokes, rich saturated canvas texture, chiaroscuro lighting, masterpiece, preserve subject exactly`
- **watercolor（水彩）**：`turn into a soft watercolor painting, gentle wet-on-wet bleeding, translucent layers, paper texture, airy negative space, preserve subject exactly`
- **watercolor-silhouette（水彩剪影）**：`turn into a soft watercolor painting in silhouette style, deep indigo-navy watercolor silhouettes, extreme negative space with mostly blank paper-white sky, only a few gentle diluted washes at the base, rough cold-press watercolor paper texture, elegant minimalism, preserve subject exactly`
- **ink（水墨剪影）**：`turn into a minimalist Chinese ink wash painting (shuimo), buildings become bold black ink silhouettes, extreme negative space with mostly blank paper-white sky, only a few dilute ink washes at the base, rough cold-press watercolor paper texture, elegant sumi-e minimalism, preserve subject exactly`
- **sketch（素描）**：`turn into a pencil sketch, clean linework and hatching, monochrome graphite texture, structural, preserve subject exactly`
- **illustration（插画）**：`turn into a flat vector illustration, limited palette, clean edges, no outlines clutter, modern editorial, preserve subject exactly`
- **vintage（复古）**：`turn into a vintage faded photograph, warm sepia tones, film grain, soft vignette, nostalgic, preserve subject exactly`

## 与相邻工序关系

- 上游 `compretouch`：提供构图正确、干净的底图；本工序只改「媒介」，不改比例与清晰度。
- 下游 `color`：在重绘图上做最终色调统一（可与媒介情绪叠加，但不抵消媒介特征）。

## 质量门禁

- 主体身份 / 姿态 / 关键特征**不变形**（人还是那个人、地标还是那个地标）。
- 媒介特征明显且统一，无半照片半画作的撕裂感。
- 未引入不属于原图的物体或文字。
- 不达标 → 重做本工序，绝不带着问题进 `color`。
