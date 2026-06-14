---
name: design-art-gallery-institutional
description: "art gallery landing-page design study — 'institutional' theme/persona (pure HTML/CSS/JS, no build). Use when designing a 'institutional'-style art gallery site aesthetic. Access is a right, not a feature. art galleryの「institutional」テーマLPのデザイン参照スキル。"
---

# design-art-gallery-institutional

A landing-page **design study** for a fictional **institutional**-theme art gallery (pure HTML + CSS + vanilla JS, no build, GitHub-Pages ready). Use this as a **style / design-system reference** when building a similar aesthetic.

架空の「institutional」テーマのart gallery LP デザイン研究。同種の世界観を作るときの**スタイル／デザインシステム参照**として使う。

## When to use / 使いどころ
- **EN:** designing a 'institutional'-style art gallery site — match its palette, typography and layout discipline.
- **JP:** 「institutional」系のart galleryサイトを設計するとき。配色・タイポ・レイアウト規律を流用。

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
| **Brand** | MASS |
| **Persona** | institutional |
| **Live Site (planned)** | `design.art-gallery-institutional.riumu.net` |

### Design Concept
- **Color**: Warm cream `#FAF7F0` × ink `#181818` × Whitney red `#DD1A21` (mission/LIVE) × institutional blue `#1A4A8E` (links)
- **Typography**: Inter Tight 600 (Söhne Breit alternate, display) × Inter (body) × EB Garamond (quotes/footnotes)
- **Aesthetic**: Editorial scholarly × sidebar footnote layout × installation views with people
- **UX**: 6-category nav (Visit / Exhibitions / Collection / Learn / Membership / About). 4-language switcher (EN / JA / ES / ZH). Sidebar metadata on hero and collection. Mission as a dark-inverted blockquote section.
- **Accessibility**: Skip-link mandatory. WCAG 2.2 AA. Reduced-motion respected. Color never the sole information channel.

### 概要
| | |
|---|---|
| **ブランド** | MASS |
| **ペルソナ** | institutional |
| **公開URL（予定）** | `design.art-gallery-institutional.riumu.net` |

### デザインコンセプト
- **カラー**: warm cream × インク黒 × Whitney red（ミッション・LIVE）× institutional blue（リンク）
- **フォント**: Inter Tight 600（Söhne Breit 代替、見出し）× Inter（本文）× EB Garamond（引用・脚注）
- **世界観**: 学術エディトリアル × サイドバー脚注 × 人物入りインスタレーション写真
- **UX**: ナビ6カテゴリ（Visit / Exhibitions / Collection / Learn / Membership / About）。4言語切替（EN / JA / ES / ZH）。ヒーローとコレクションにサイドバーメタ。Mission はダーク反転 blockquote。
- **アクセシビリティ**: skip-link 必須、WCAG 2.2 AA、prefers-reduced-motion 対応、色のみで情報を伝えない

## Tech / 技術
- Pure HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN (Inter + Inter Tight + EB Garamond)
- No framework, no build step — GitHub Pages ready

## How to apply / 適用方法
1. Reuse `style.css` custom properties (color / type / spacing tokens) as the design-system base.
2. Copy `index.html` layout as the starting structure, then swap brand name and content.
3. Keep the palette, font pairing and layout discipline described above.

---
> The brand is fictional (design study) — replace all brand/content. Full context: see **`README.md`**.
