[English](#english) | [日本語](#japanese)

---

<a id="english"></a>

# MASS — design-art-gallery-institutional

> **"Access is a right, not a feature."**

A design study exploring a fictional public modern-art museum — MoMA / Tate / Whitney / Walker Art Center tier — targeting **students, researchers, families, and general visitors across all ages**, with mission-led editorial, multilingual UI, and WCAG 2.2 AA enforcement.

MASS is a fictional museum created for this design study. It is not a real museum, institution, artist, or work.

## Overview

| | |
|---|---|
| **Brand** | MASS |
| **Persona** | institutional |
| **Live Site (planned)** | `design.art-gallery-institutional.riumu.net` |

## Design Concept

- **Color**: Warm cream `#FAF7F0` × ink `#181818` × Whitney red `#DD1A21` (mission/LIVE) × institutional blue `#1A4A8E` (links)
- **Typography**: Inter Tight 600 (Söhne Breit alternate, display) × Inter (body) × EB Garamond (quotes/footnotes)
- **Aesthetic**: Editorial scholarly × sidebar footnote layout × installation views with people
- **UX**: 6-category nav (Visit / Exhibitions / Collection / Learn / Membership / About). 4-language switcher (EN / JA / ES / ZH). Sidebar metadata on hero and collection. Mission as a dark-inverted blockquote section.
- **Accessibility**: Skip-link mandatory. WCAG 2.2 AA. Reduced-motion respected. Color never the sole information channel.

## Tech Stack

- Pure HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN (Inter + Inter Tight + EB Garamond)
- No framework, no build step — GitHub Pages ready

## Spec

See [spec.md](./spec.md) for the full design specification.

## Part of

This repository is one of four design studies under the **art-gallery persona series**:

| Persona | Brand | Aesthetic |
|---------|-------|-----------|
| bluechip | NORE | Museum-grade white cube |
| emerging | HALF | DIY zine, anti-luxury |
| digital | HEX | Terminal, Web3 native |
| **institutional** | MASS | Scholarly, multilingual |

Navigator: [art-gallery](../README.md)

---

<a id="japanese"></a>

# MASS — design-art-gallery-institutional（日本語）

> **「アクセスは権利であって機能ではない」**

公立現代美術館（MoMA / Tate / Whitney / Walker Art Center 級）のデザイン研究。**学生・研究者・家族連れ・一般来館者という年齢層の広い来訪者全員** に向けて、ミッション主導のエディトリアル・多言語UI・WCAG 2.2 AA 準拠で構築する架空美術館のサイトです。

MASS は本デザイン研究のために作成した架空美術館です。実在の機関・館・作家・作品ではありません。

## 概要

| | |
|---|---|
| **ブランド** | MASS |
| **ペルソナ** | institutional |
| **公開URL（予定）** | `design.art-gallery-institutional.riumu.net` |

## デザインコンセプト

- **カラー**: warm cream × インク黒 × Whitney red（ミッション・LIVE）× institutional blue（リンク）
- **フォント**: Inter Tight 600（Söhne Breit 代替、見出し）× Inter（本文）× EB Garamond（引用・脚注）
- **世界観**: 学術エディトリアル × サイドバー脚注 × 人物入りインスタレーション写真
- **UX**: ナビ6カテゴリ（Visit / Exhibitions / Collection / Learn / Membership / About）。4言語切替（EN / JA / ES / ZH）。ヒーローとコレクションにサイドバーメタ。Mission はダーク反転 blockquote。
- **アクセシビリティ**: skip-link 必須、WCAG 2.2 AA、prefers-reduced-motion 対応、色のみで情報を伝えない

## 技術

- 純粋な HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN（Inter + Inter Tight + EB Garamond）
- ビルド不要で GitHub Pages 対応

## 仕様書

詳細は [spec.md](./spec.md) を参照。

## シリーズ

このリポジトリはアートギャラリー・ペルソナシリーズ4作のうちの1つ。
ナビゲーターページ: [art-gallery](../README.md)
