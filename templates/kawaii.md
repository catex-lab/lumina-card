# 模板：Kawaii（可爱水彩 / 童话绘本）

**情绪**：可爱、治愈、温柔、像童书绘本里的城市或人物。把照片变成马卡龙水彩插画。

## 配色

| 角色 | 色值 | 用途 |
| --- | --- | --- |
| 页面底色 | `#FFF9F7`（奶油粉白） | 外层背景 |
| 卡片底色 | `#FFFDFB`（暖白） | 明信片卡片本体 |
| 主粉 | `#FFB7C5` / `#FF9EB0` | 装饰圆点、标题点缀 |
| 薄荷 | `#B8E0D2` / `#A3D2C2` | 英文副标、次要装饰 |
| 奶黄 | `#FFF0B5` | 装饰圆点 |
| 文字 | `#5A4A55` 主 / `#C4A6B2` 次要 | 中文标题与正文 |

**铁律**：全片保持马卡龙低饱和色系，避免高对比、避免黑色、避免硬边阴影；用柔和的投影和虚线/圆点装饰。

## 字体

- 中文：霞鹜文楷 / 苹方 / 楷体（手写圆润感）
- 英文：Brush Script MT / Pacifico / Comic Sans MS（手写体）

## 排版

- 卡片大圆角（约 36px），整体像一张贴纸
- 顶部一行小字 eyebrow（如 `KAWAII WATERCOLOR`）
- 主图圆角包裹，带柔和阴影
- 标题圆润、可局部用粉色点缀
- 英文用手写体斜置，制造轻松感
- 底部小字标语，字母间距略宽
- 装饰：散布圆点、虚线圈、云朵感色块

## 底图（ImageGen 提示）

- 中文：「把这张照片转成可爱水彩绘本插画风格，柔和马卡龙粉彩色系，水彩晕染与留白质感，圆润软萌造型，画面温暖治愈，纯手绘感，无文字，无边框」
- 英文：`Transform this photo into a cute kawaii watercolor picture-book illustration, soft pastel macaron color palette, dreamy watercolor washes with paper texture and white space, rounded adorable shapes, warm and cozy hand-painted style, no text, no border`
- 关键点：`kawaii watercolor` + `pastel macaron` + `rounded shapes` + `paper texture / white space`

## 成品模板（测试版）

已提供可复用版式 `templates/kawaii.html`，自带占位符：

- `{{IMAGE}}` —— kawaii watercolor 底图文件名（与本 html 同目录）
- `{{EYEBROW}}` —— 顶部小字（如 `KAWAII WATERCOLOR`）
- `{{TITLE}}` —— 中文标题
- `{{EN}}` —— 英文手写字副标
- `{{SUB}}` —— 一行正文 / 标语

**已知限制**：ImageGen 当前最大尺寸 1024×1536，短边 1024px，低于 1600px 印刷底线；要印刷需先超分底图。

## 适用

童话感城市、治愈风景、可爱人像/宠物、下午茶/美食、游乐场、樱花等温暖主题。不适合严肃商务或高对比建筑摄影。
