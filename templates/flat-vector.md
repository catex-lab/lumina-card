# 模板：Flat Vector（有限色系矢量扁平 / 插画艺术）

**情绪**：简洁、现代、轻盈、像一幅插画艺术印刷品。保留照片的辨识内容，但用纯扁平色块重新表达。

## 配色

| 角色 | 色值 | 用途 |
| --- | --- | --- |
| 页面底色 | `#F5F2EC`（暖灰白） | 外层背景 |
| 卡片底色 | `#FBF9F4`（暖白） | 明信片卡片本体 |
| 深墨绿 | `#3A4A43` | 主文字 / 深色块 |
| 陶土橙 | `#C97B4A` | 强调色：小色块印章 |
| 灰 | `#A8A29A` | 次要文字 |

**铁律**：全片 3–4 个色相（墨绿 + 陶土橙 + 暖白灰阶），与底图的有限色系呼应；无轮廓线、无渐变、无纹理。装饰仅用克制的小色块/圆点，不引入外框线。

## 字体

- 中文：思源黑体 / 苹方（Light–Regular，字重轻盈）
- 英文：Georgia / 衬线体小标

## 排版

- 居中构图、充足留白、无外框，像艺术画册单页
- 顶部一行小字 eyebrow（如 `VECTOR FLAT`）
- 主图居中、偏上，宽度约 86%，四周留白充足
- 标题字重轻（Light）、大字距，营造呼吸感
- 文字区下沉，英文小标 + 一行短句收尾
- 装饰：右上角一小块陶土橙色块 + 左下角深色小圆点，点到即止

## 底图（ImageGen 提示）

- 中文：「把这张照片转成有限色系扁平矢量插画，3-4 种配色，无轮廓线条，纯矢量扁平风格，留白空间，居中构图，简洁现代，无文字，无边框」
- 英文：`Transform this photo into a clean flat vector illustration: very limited color palette of only 3-4 flat muted colors, no outlines no strokes, pure flat vector style like modern illustration art, generous negative space, centered composition, simple and elegant, no texture, no gradient, no text, no border`
- 关键点：`flat vector illustration` + `limited color palette 3-4` + `no outlines no strokes` + `negative space` + `centered composition`

## 成品模板（测试版）

已提供可复用版式 `templates/flat-vector.html`，自带占位符：

- `{{IMAGE}}` —— 矢量扁平底图文件名（与本 html 同目录）
- `{{EYEBROW}}` —— 顶部小字（如 `VECTOR FLAT`）
- `{{TITLE}}` —— 中文标题
- `{{EN}}` —— 英文副标
- `{{SUB}}` —— 一行正文 / 标语

**已知限制**：ImageGen 当前最大尺寸 1024×1536，短边 1024px，低于 1600px 印刷底线；要印刷需先超分底图。

## 适用

城市、建筑、风景、静物、交通工具等任何题材均可，风格通用性强。人像也适合（扁平化后温柔不恐怖）。不适合需要写实细节的场景。
