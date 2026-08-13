# Gongbi · 中式工笔画风格

## 一句话定义
把照片转为「淡彩工笔 + 宣纸底」的中式插画：精细墨线勾勒、矿物色薄染、保留主体特征、弱化杂乱背景。

## 视觉铁律
1. **线描**：主体轮廓用细而均匀的墨线勾勒，忌粗黑描边或卡通线。
2. **设色**：低饱和矿物色——花青、赭石、藤黄、淡朱，薄而透明。
3. **背景**：干净宣纸底色，带轻微纤维纹理，**删除或弱化天空、人群、杂乱建筑、广告牌等无效信息**。
4. **主体**：东方明珠/主体建筑特征必须保留且可识别，但适度简化和艺术化。
5. **留白**：中国画式留白，不填满画面；主体偏中下，天空大面积留空。
6. **无阴影/无渐变块**：以线条和淡淡分染表现体积，不出现西画式投影。

## 输出规格
- 比例：竖版 2:3 明信片（推荐 1024×1536）
- 安全边距：四周至少 50px 等效出血
- 无文字、无 UI、无水印（尽量）、无现代字体/西画阴影

## ImageGen 提示词（中英文混合，强制约束）

```
Transform this photo of a Shanghai cityscape into a Chinese traditional gongbi (fine-brush) painting: delicate fine ink outline strokes, soft muted mineral-pigment colors (pale azurite blue, light ochre, soft moss green, faint cinnabar), keep the main subject (Oriental Pearl Tower and skyline) clearly recognizable and accurate, remove or weaken cluttered background details, clean warm xuan paper (rice paper) background with subtle natural fiber texture, high definition, elegant and refined, no text, no border. 把照片转成中式工笔画风格，精细淡彩线条，保留主体特征，弱化无效背景信息，干净宣纸底，高清画质。
```

## 版式模板
- 文件：`templates/gongbi.html`
- 占位符：
  - `{{IMAGE}}` — 工笔画风格底图路径
  - `{{EYEBROW}}` — 刊头小字（如「上海 · 东方明珠」）
  - `{{TITLE}}` — 主标题中文（如「东方雅集」）
  - `{{EN}}` — 英文副题（如「Oriental Elegance」）
  - `{{SUB}}` — 底部诗句/短句（如「一江烟水，十里繁华，入画来。」）
  - `{{SEAL}}` — 右下角朱红印章文字（1-2 字，如「浮光」）

## 版式要点
- 宣纸暖白底 #F4EFE2，双层细线边框（外金线 + 内墨线）。
- 主图居中偏上，底部自然过渡到文字区。
- 中文标题用思源宋体（Noto Serif SC），字距舒朗，体现中式排版。
- 英文副题用斜体 Cormorant Garamond，小字烘托。
- **朱红印章**是点睛：右下角一方红印，印文 1-2 字，白文/朱文均可。
- 整体留白 ≥ 50%。

## 示例文案
- EYEBROW：上海 · 东方明珠
- TITLE：东方雅集
- EN：Oriental Elegance
- SUB：一江烟水，十里繁华，入画来。
- SEAL：浮光

## 验收标准
- [ ] 主体可识别（东方明珠/建筑轮廓准确）。
- [ ] 线条细、均匀、无西画硬阴影。
- [ ] 背景干净，无杂乱元素。
- [ ] 宣纸底自然，不塑料。
- [ ] 印章与中式排版协调。
