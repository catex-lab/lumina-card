# Lumina Card · 浮光卡片

> Turn any photo into a printable, shareable postcard — via a 6-step pipeline.

English ｜ [简体中文](./README.md)

## ✨ Features

- **6-step pipeline**: analyze → lock subject → retouch → color → design → QC
- **Built-in styles**: `classic` (warm white + gold edge, default), `silhouette` (two-tone flat)
- **Extensible**: drop a `<name>.md` (+ optional `<name>.html`) into `templates/` — no core changes needed
- **Bilingual**: triggers on both English and Chinese commands

## 📦 Install

```bash
# User-level (global, recommended)
git clone https://github.com/catex-lab/lumina-card.git ~/.workbuddy/skills/lumina-card

# Project-level (this project only)
git clone https://github.com/catex-lab/lumina-card.git <your-project>/.workbuddy/skills/lumina-card
```

## 🚀 Usage

1. Upload a photo in WorkBuddy.
2. Say: `postcard` / `做成明信片` / `生成贺卡`.
3. The skill runs the full pipeline automatically. To pick a style, say: `use classic template` / `用 silhouette 模板`.

## 🖼️ Showcase

> Source: Shanghai · Oriental Pearl Tower skyline

| `classic` (warm white + gold edge) | `silhouette` (two-tone flat) |
| --- | --- |
| ![classic](./showcase/showcase-classic.png) | ![silhouette](./showcase/showcase-silhouette.png) |

## 🎨 Built-in Styles

| Style | Description | Layout |
| --- | --- | --- |
| `classic` | Warm white background with a fine gold edge — bright and safe for most photos | `templates/classic.html` |
| `silhouette` | Two-tone flat silhouette, bold shapes — great for landmarks and skylines | `templates/silhouette.html` |

## 🧩 Add a New Style

1. Create `templates/<name>.md` — style spec: mood, palette, fonts, layout, ImageGen prompt.
2. Optional: create `templates/<name>.html` — reusable layout with `{{IMAGE}}` etc. placeholders.
3. The pipeline auto-detects it — no need to edit `SKILL.md` or `prompts/`.

## ⚠️ Known Limits

- ImageGen costs ~5–10 credits per generated image.
- Output short edge is 1024px; supersample to ≥1600px before printing.

## 📄 License

MIT © 2026 catex-lab
