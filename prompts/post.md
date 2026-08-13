# 工序 6 — 版式排版 (Post)

**目标**：把 `color` 调色后的成品图，套用选定模板，完成版式、边框、文字与用户签名，产出最终明信片。**本工序只负责「装裱」——艺术化（绘画媒介重绘）已在 `art-transform` 完成，本工序不再改变图像本身的画风。**

**输入**：color 图 + 模板规范（`templates/<name>.md`）+ 用户文案 + 用户署名（`{{SIGNATURE}}`）。

**步骤**：

1. 读取模板规范：版式、边框、配色、字体、留白、文字位置。
2. 套用版式：将图像放入模板指定区域（满版 / 带边 / 分栏 / 偏置留白）。
3. 加文字：标题（地点 / 主题）+ 可选寄语，严格按模板字体与位置，保证可读。
4. 边框 / 装饰：按模板添加（classic 细金边 / vintage 做旧边 / minimal 无框 / editorial 网格线）。
5. 叠加用户签名（详见 `prompts/brand-mark.md`）：在版式右下安全角放置**独立设计叠加层**，由用户自定义署名 `{{SIGNATURE}}`（昵称/名称/工作室，缺失时回退 `Lumina Card`）。可选前缀光圈图标 `{{BRANDMARK}}`（`assets/brandmark.svg`）。满足低调、可读、不压主体、不与主标题竞争。运行时把 brandmark.svg 复制到与 HTML 同目录并填入 `{{BRANDMARK}}`。
6. 产出成品：
   - **classic**（内置默认）：用内置 HTML 版式 `templates/classic.html`，填底图、文案与 `{{SIGNATURE}}`/`{{BRANDMARK}}` 后渲染 / 截图交付（中文清晰可控）。
   - **silhouette**（内置）：用内置 HTML 版式 `templates/silhouette.html`，填底图、文案与 `{{SIGNATURE}}`/`{{BRANDMARK}}` 后渲染 / 截图交付（双色剪影、大留白、厚重扁平）。
   - **sticker**（内置）：用内置 HTML 版式 `templates/sticker.html`，填底图、文案与 `{{SIGNATURE}}`/`{{BRANDMARK}}` 后渲染 / 截图交付（模切贴纸插画、干净纯色底、大圆角可爱风）。
   - **minimal / vintage**（待补版式）：可用 ImageGen 图生图直接合成（无复杂文字时）；若需 HTML 可控文字，补 `templates/<name>.html` 后套用。
7. 输出明信片成品，进入 `qc.md`。

## 扩展新风格

在 `templates/` 下新增 `<name>.md`（风格规范）+ 可选 `<name>.html`（可复用版式）即可，**无需改 SKILL.md 或本文件**——流水线按 `<name>` 自动查找。`classic`、`silhouette` 与 `sticker` 已作为内置成品风格固化（见各自 `.html` 版式）。

**文案规则**：

- 用户提供文案 → 直接用。
- 文案缺失 → 给 2–3 个候选请用户定，不擅自编造大段文字。
- 字体：模板指定中文用思源 / 苹方类；英文用模板指定字体；避免生僻字体导致渲染失败。

**质量门禁（设计侧）**：

- 文字可读、无溢出 / 重叠、位置符合模板。
- 边框 / 装饰符合模板。
- 整体美观、主体突出、一眼看懂「讲什么」。
- 用户签名低调可读、未压主体、未与标题竞争。
