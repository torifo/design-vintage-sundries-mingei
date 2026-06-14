---
name: design-vintage-sundries-mingei
description: "vintage sundries / zakka shop landing-page design study — 'mingei' theme/persona (pure HTML/CSS/JS, no build). Use when designing a 'mingei'-style vintage sundries / zakka shop site aesthetic. What the hand remembers. vintage sundries / zakka shopの「mingei」テーマLPのデザイン参照スキル。"
---

# design-vintage-sundries-mingei

A landing-page **design study** for a fictional **mingei**-theme vintage sundries / zakka shop (pure HTML + CSS + vanilla JS, no build, GitHub-Pages ready). Use this as a **style / design-system reference** when building a similar aesthetic.

架空の「mingei」テーマのvintage sundries / zakka shop LP デザイン研究。同種の世界観を作るときの**スタイル／デザインシステム参照**として使う。

## When to use / 使いどころ
- **EN:** designing a 'mingei'-style vintage sundries / zakka shop site — match its palette, typography and layout discipline.
- **JP:** 「mingei」系のvintage sundries / zakka shopサイトを設計するとき。配色・タイポ・レイアウト規律を流用。

## Bundled assets / 同梱アセット
This skill folder is the reference implementation — start from these files:
- `index.html` — full page markup
- `style.css` — design tokens (CSS custom properties) + layout
- `script.js` — vanilla JS (if present)
- `README.md` — full bilingual doc, brand context and series links

## Design reference / デザイン参照
_Lifted from the repo README — see README.md for the complete, bilingual version._

### Overview
| | |
|---|---|
| **Brand** | TSUCHI to ITO (土と糸) |
| **Persona** | mingei (Folk craft) |
| **Live Site (planned)** | `design.vintage-sundries-mingei.riumu.net` |

### Design Concept
- **Color**: Indigo `#1d3a5f` × iron-rust brown `#7a4a2d` × unbleached linen `#f3ecdc` × vermilion seal `#a8412c`
- **Typography**: Shippori Mincho B1 (display) × Noto Serif JP (body) × Sawarabi Mincho (kana)
- **Aesthetic**: Yanagi Soetsu's mingei movement × washi paper texture × vertical-rl typesetting
- **UX**: Vertical-rl pull-quotes, seal-stamped store note, 4 articles ("yomimono"), and 4 "shop principles" in dark-inverted block
- **Texture**: SVG washi noise with `mix-blend-mode: multiply`

### 概要
| | |
|---|---|
| **ブランド** | 土と糸（TSUCHI to ITO） |
| **ペルソナ** | mingei（民藝） |
| **公開URL（予定）** | `design.vintage-sundries-mingei.riumu.net` |

### デザインコンセプト
- **カラー**: 紺藍 × 鉄錆 × 生成り × 朱印（アクセント）
- **フォント**: Shippori Mincho B1（見出し）× Noto Serif JP（本文）× Sawarabi Mincho（かな）
- **世界観**: 柳宗悦的民藝運動 × 和紙テクスチャ × 縦書き混在
- **UX**: 縦書き引用、店主一筆（朱印付き）、読みもの4本、店の信条4条（ダーク反転）
- **テクスチャ**: SVG 和紙ノイズ＋暖色 multiply

## Tech / 技術
- Pure HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN (Shippori Mincho B1 + Noto Serif JP + Sawarabi Mincho)
- No framework, no build step — GitHub Pages ready

## How to apply / 適用方法
1. Reuse `style.css` custom properties (color / type / spacing tokens) as the design-system base.
2. Copy `index.html` layout as the starting structure, then swap brand name and content.
3. Keep the palette, font pairing and layout discipline described above.

---
> The brand is fictional (design study) — replace all brand/content. Full context: see **`README.md`**.
