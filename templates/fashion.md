# Fashion Editorial · 极简抽象时尚插图

## 一句话定义
把照片转为「电影感柔光 + 柔和阴影 + 大留白」的当代时尚编辑插图；整体精致、克制、杂志化。

## 视觉铁律
1. **光影**：cinematic soft lighting，柔和的漫射光，阴影轻淡不锐利。
2. **色彩**：低饱和高级中性色——米白、燕麦、鼠尾草灰绿、暖灰褐；禁止荧光/高饱和。
3. **造型**：建筑/主体抽象为圆润几何体，边缘干净但不锐利；保留辨识度，不卡通化。
4. **空间**：大量负空间，主体偏中下或居中，背景极简几乎纯色。
5. **质感**： matte（哑光），无颗粒、无纹理、无描边、无渐变条。
6. **情绪**： refined, elegant, high-end editorial，像 Vogue/Monocle 插画页。

## 输出规格
- 比例：竖版 2:3 明信片（推荐 1024×1536）
- 安全边距：四周至少 40px 等效出血
- 无文字、无水印、无 UI、无黑色轮廓线

## ImageGen 提示词（中英文混合，强制约束）

```
Transform this photo into a minimalist abstract fashion illustration: cinematic soft lighting, gentle soft shadows, clean minimal background, generous negative space, contemporary editorial illustration style, refined and elegant, sophisticated muted color palette, high-end magazine aesthetic, smooth matte shapes, no outlines, no text, no border. 把照片转成极简抽象时尚插图，电影般柔光，柔和阴影，干净极简背景，负空间，当代编辑插图，精致美观。
```

## 版式模板
- 文件：`templates/fashion.html`
- 占位符：
  - `{{IMAGE}}` — 风格化底图路径
  - `{{EYEBROW}}` — 刊头小字（如「SHANGHAI」）
  - `{{TITLE}}` — 主标题中文（如「东方诗学」）
  - `{{EN}}` — 英文副题（如「Oriental Minimalism」）
  - `{{SUB}}` — 底部短句/日期/地点

## 版式要点
- 底图全出血，底部做暖白渐变蒙版自然过渡。
- 文字卡半透明白色 + 轻微模糊，居中置于底部约 1/4 处。
- 标题用 Playfair Display（衬线、优雅），字重 500，字距紧致。
- 右上角 1 根细金线 + 1 点作为克制装饰。
- 整体留白 ≥ 55%。

## 示例文案
- EYEBROW：SHANGHAI
- TITLE：东方诗学
- EN：Oriental Minimalism
- SUB：黄浦江畔，晨雾未散，城市在柔光中醒来。

## 验收标准
- [ ] 一眼高级：配色低饱和、无廉价感。
- [ ] 柔光明显，没有硬边投影。
- [ ] 负空间充足，不拥挤。
- [ ] 无文字/水印入侵主体。
