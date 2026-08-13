# 模板：Silhouette（极简剪影 / 双色扁平）

**情绪**：极简、现代、克制、像一张海报。把照片压成最少信息的剪影图形。

## 配色

| 角色 | 色值 | 用途 |
| --- | --- | --- |
| 底色 | `#F2EFE8`（暖米）或其他纯色 | 整版背景，单一纯色，无渐变 |
| 剪影 | `#1A1A1A` 等单深色 | 主体图形，纯色块 |
| 文字 | `#2A2A2A` 主 / `#7A7A7A` `#5A5A5A` `#8A8A8A` 灰阶 | 灰阶文字，不抢剪影 |
| 强调 | 无（保持双色） | 不引入第三色 |

**铁律**：全图只出现「底色 + 剪影色」两色；文字仅用灰阶，不破坏双色基调。

## 字体

- 中文：思源黑体 / 苹方 Bold
- 英文：Georgia / 无衬线，作小标

## 排版

- 大留白、居中、无框、无装饰线
- 顶部一行小字（eyebrow，如 `MINIMAL SILHOUETTE`）
- 底部：超大中文标题（粗黑、大字距）+ 小号英文 + 一行日期/标语
- 图像满宽、扁平方正，视觉重心在图形本身

## 底图（ImageGen 提示）

- 中文：「把这张照片转成双色剪影海报，单一深色剪影 + 纯色浅底，厚重扁平造型，无渐变无纹理，强对比，矢量海报风，无文字」
- 英文：`minimalist two-tone duotone poster of this photo, bold flat silhouette in a single dark color on a solid flat light background, only two colors, no gradients, no texture, clean vector poster style, no text, no border`
- 关键点：`only two colors` + `no gradients` + `bold flat shapes` + `thick geometric forms`

## 成品模板（内置）

已提供可复用版式 `templates/silhouette.html`，自带占位符：

- `{{IMAGE}}` —— 双色剪影底图文件名（与本 html 同目录）
- `{{EYEBROW}}` —— 顶部小字（如 `MINIMAL SILHOUETTE`）
- `{{TITLE}}` —— 中文大标题
- `{{EN}}` —— 英文副标
- `{{SUB}}` —— 一行正文 / 标语

**填充实例**：`postcard-output/postcard4.html`（东方明珠图，双色剪影 + 暖米底）。

**已知限制**：ImageGen 当前最大尺寸 1024×1536，短边 1024px，低于 1600px 印刷底线；要印刷需先超分底图。

## 适用

地标、建筑、城市天际线、任何「轮廓够强」的图。主体轮廓越利落，剪影越出彩。人像/宠物也可用，但需背景干净。
