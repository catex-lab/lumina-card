# sticker 风格规范

## 视觉关键词
贴纸风 / die-cut sticker / 干净纯色背景 / 模切白边 / 圆润卡通 / 轻投影 / 可爱治愈

## 使用场景
旅行纪念品、城市伴手礼、年轻女性/儿童市场、文创周边。

## 色彩
- 主底：薄荷奶油 `#E8F5E9`（干净、柔和、不抢贴纸主体）
- 文字：深绿灰 `#3E4A42`
- 强调：珊瑚橙 `#FF8A65`
- 点缀：浅绿 `#81C784`、暖黄 `#FFD54F`

## 字体
- 标题：圆润粗黑 / Nunito ExtraBold，中文建议「思源黑体 Heavy」或系统黑体加粗
- 英文：Nunito SemiBold / 同系列无衬线
- 副文案：中等字重、适度字距

## 版式要点
1. 主图是「贴纸插画」本身：必须带白色模切描边/轮廓，与纯色底形成清晰边界。
2. 贴纸居中偏上，下方留足空间给标题。
3. 明信片卡片整体用大圆角（24–32px），内嵌浅色描边，模拟贴纸卡片质感。
4. 顶部可加三个彩色小圆点，暗示贴纸册/手账氛围。
5. 用户签名放在右下角，opacity 0.42，不与可爱主标题竞争。

## ImageGen 图生图提示词（参考）
> Transform this photo into a cute die-cut sticker illustration with a thick white die-cut border outline around the whole subject, clean solid pastel background, rounded cartoon forms, gentle cheerful colors, subtle drop shadow under the sticker, no texture, no text, no frame.
> 把照片转成可爱模切贴纸插画，整体带厚厚白色描边轮廓，干净纯色背景，圆润卡通造型，活泼柔和配色，轻微投影，无纹理，无文字，无边框。

## 占位符
- `{{IMAGE}}`：贴纸风底图
- `{{EYEBROW}}`：眉题（如 `TRAVEL STICKER`）
- `{{TITLE}}`：主标题（城市名/主题）
- `{{EN}}`：英文副标题
- `{{SUB}}`：小字文案
- `{{SIGNATURE}}`：用户自定义署名（昵称/名称/工作室，缺失回退 `Lumina Card`）
- `{{BRANDMARK}}`：`assets/brandmark.svg` 光圈图标路径（可选前缀，与签名文字同现）

## 输出规格
- 明信片竖版 2:3
- 模板 HTML 宽度 600px，最终 2x 渲染 1200px
