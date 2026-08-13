# 浮光卡片 · Lumina Card

> Turn any photo into a printable, shareable postcard — via a 6-step pipeline.

把任意照片，经六道工序，变成有设计感、可直接印刷或分享的明信片。

## ✨ Features

- **6-step pipeline**: analyze → lock subject → retouch → color → design → QC
- **Built-in styles**: `classic` (warm white + gold edge, default), `silhouette` (two-tone flat)
- **Extensible**: drop `<name>.md` (+ optional `<name>.html`) into `templates/` — no core changes needed
- **Bilingual**: triggers in both Chinese and English

## 📦 Install

```bash
# User-level (global, recommended)
git clone https://github.com/catex-lab/lumina-card.git ~/.workbuddy/skills/lumina-card

# Project-level
git clone https://github.com/catex-lab/lumina-card.git <your-project>/.workbuddy/skills/lumina-card
```

## 🚀 Usage

1. Upload a photo in WorkBuddy.
2. Say: `做成明信片` / `postcard` / `生成贺卡`.
3. The skill runs the full pipeline. To pick a style: `用 silhouette 模板` / `use classic template`.

## ⚠️ Limits

- ImageGen costs ~5–10 credits per generated image.
- Output short edge is 1024px; supersample to ≥1600px before printing.

## 🧩 Add a new style

1. Create `templates/<name>.md` (style spec: mood, palette, fonts, layout, ImageGen prompt).
2. Optional: create `templates/<name>.html` (reusable layout with `{{IMAGE}}` etc. placeholders).
3. The pipeline auto-detects it — no need to edit `SKILL.md` or `prompts/`.

## 📄 License

MIT © 2026 catex-lab
