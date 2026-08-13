# 浮光卡片 · Lumina Card

> 把任意照片，经六道工序，变成有设计感、可直接印刷或分享的明信片。

[English](./README.en.md) ｜ 简体中文

## ✨ 特性

- **六道工序流水线**：识别原图 → 锁定主体 → 高清清理 → 高级调色 → 套用模板设计 → 最终验收
- **内置成品风格**：`classic`（暖白底 + 细金边，默认）、`silhouette`（双色扁平剪影）
- **可扩展**：往 `templates/` 放一个 `<name>.md`（+ 可选 `<name>.html`）即可新增风格，无需改动核心代码
- **双语触发**：中英文指令都能唤起本 skill

## 📦 安装

```bash
# 用户级（全局可用，推荐）
git clone https://github.com/catex-lab/lumina-card.git ~/.workbuddy/skills/lumina-card

# 项目级（仅当前项目可用）
git clone https://github.com/catex-lab/lumina-card.git <你的项目>/.workbuddy/skills/lumina-card
```

## 🚀 使用

1. 在 WorkBuddy 里上传一张照片。
2. 说「做成明信片 / 生成贺卡 / postcard」。
3. Skill 会自动跑完整流水线。要指定风格时说「用 silhouette 模板 / 用 classic 模板」。

## 🖼️ 效果展示

> 示例原图：上海 · 东方明珠天际线（照片版权归拍摄者所有，详见文末版权声明）

| 原图 | `classic`（暖白底细金边） | `silhouette`（双色扁平剪影） |
| --- | --- | --- |
| ![原图](./showcase/source-shanghai.jpg) | ![classic](./showcase/showcase-classic.png) | ![silhouette](./showcase/showcase-silhouette.png) |

> 更多示例原图见 [`showcase/source-bund.jpg`](./showcase/source-bund.jpg)。

## 🎨 内置风格

| 风格 | 说明 | 版式 |
| --- | --- | --- |
| `classic` | 暖白底 + 细金边，明亮温暖，适合绝大多数照片 | `templates/classic.html` |
| `silhouette` | 双色扁平剪影、厚重造型，适合地标与天际线 | `templates/silhouette.html` |

## 🧩 新增风格

1. 创建 `templates/<name>.md`：风格规范（情绪、配色、字体、排版、ImageGen 提示词）。
2. 可选：创建 `templates/<name>.html`：可复用版式（含 `{{IMAGE}}` 等占位符）。
3. 流水线自动识别，无需修改 `SKILL.md` 或 `prompts/`。

## ⚠️ 已知限制

- ImageGen 出图约消耗 5–10 credits/张。
- 产物短边 1024px，如需印刷请先超分至 ≥1600px。

## 📄 许可证

**Skill 代码**：MIT © 2026 catex-lab

**示例照片版权**：`showcase/` 目录下的所有示例照片（`source-shanghai.jpg` / `source-bund.jpg` 及由其生成的成品图）版权归拍摄者 **catex-lab** 所有（© 2026 catex-lab），仅用于本仓库效果展示，**禁止擅自商用、转载或二次分发**。如需使用请先联系作者。
