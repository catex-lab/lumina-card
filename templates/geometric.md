# 模板：Geometric（极简抽象几何 / 矢量扁平）

**情绪**：极简、抽象、现代、像艺术画廊海报。把照片提炼成最少的几何形状与色彩关系。

## 配色

| 角色 | 色值 | 用途 |
| --- | --- | --- |
| 页面底色 | `#F4F2EC`（暖灰白） | 外层背景 |
| 卡片底色 | `#FAF8F3`（暖白） | 明信片卡片本体 |
| 墨蓝 | `#2B3852` | 主文字 / 深色块 |
| 赭橙 | `#C96F2E` | 强调色：角标、圆点、细线 |
| 灰 | `#A09A8E` | 次要文字 |

**铁律**：全片仅 3–4 个色相（此处墨蓝 + 赭橙 + 暖白灰阶），与底图的有限色系呼应；不引入高饱和新色。所有装饰为几何元素（细线框、角标、圆点），无曲线装饰、无手写体。

## 字体

- 中文：思源黑体 / 苹方（Regular–Bold）
- 英文：Georgia / 衬线体小标，或 Helvetica 式无衬线

## 排版

- 居中构图、极大留白，整体像一张艺术展海报
- 顶部一行小字 eyebrow（如 `ABSTRACT GEOMETRY`）
- 主图居中、偏上，宽度约 88%，四周留白充足
- 文字区下沉至底部，用一根短橙色细线收尾
- 装饰：外圈细线框 + 四角橙色直角角标 + 少量圆点，克制不喧宾夺主

## 底图（ImageGen 提示）

- 中文：「把这张照片转成极简抽象几何图形设计，几何形状概括城市天际线，有限色系（3-4 色），无轮廓线条，矢量扁平风格，极度留白空间，居中构图，无文字，无边框」
- 英文：`Transform this photo into a minimalist abstract geometric composition: simplified geometric shapes abstracting the skyline, very limited color palette of only 3-4 muted colors, no outlines no strokes, flat vector style, extreme negative space, centered composition, minimal modern art poster look, no text, no border`
- 关键点：`minimalist abstract geometric` + `limited color palette 3-4 colors` + `no outlines` + `flat vector` + `extreme negative space` + `centered composition`

## 成品模板（测试版）

已提供可复用版式 `templates/geometric.html`，自带占位符：

- `{{IMAGE}}` —— 抽象几何底图文件名（与本 html 同目录）
- `{{EYEBROW}}` —— 顶部小字（如 `ABSTRACT GEOMETRY`）
- `{{TITLE}}` —— 中文标题
- `{{EN}}` —— 英文副标
- `{{SUB}}` —— 一行正文 / 标语

**已知限制**：ImageGen 当前最大尺寸 1024×1536，短边 1024px，足够高清屏幕预览与社交分享；如需实体印刷（≥1600px 短边），须将重绘底图先做 2× 超分。

## 适用

地标、城市天际线、建筑局部、海平线、山形等「轮廓抽象后仍有辨识度」的题材。不适合细节丰富的花鸟/人像特写（抽象化后易失真）。
