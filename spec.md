# MASS — design-art-gallery-institutional Spec

**Status:** Approved
**Author:** torifo
**Created:** 2026-05-22
**Updated:** 2026-05-22

---

## 1. Overview

### Problem Statement
公立美術館・大学美術館・ファウンデーション系（MoMA / Tate / Whitney / Walker Art Center 級）のWebサイトは、ミッション・教育・公共性を伝える責任を負うが、多くのサイトでは「カタログ的羅列」か「広告的フラッシュ」のどちらかに偏り、研究者・学生・一般来館者という多様な来訪者の知的好奇心を一様には満たせない。エディトリアル的な情報密度と、誰でも入れる導線の両立が課題。

### Goal
"MASS"（量塊、博物館的重量感）という架空の現代美術館のランディングページを実装し、**学術的エディトリアル × サイドバー脚注式メタデータ × 多言語前提UI × ミッションステートメント前面化** が、商業ギャラリーとは別軸の信頼を生むことを検証する。

### Non-Goals
- EC機能・チケット販売（リンクのみ、本サイトでは処理しない）
- リアルタイム展覧会データフィード
- ソーシャル機能（コメント・シェア統計）
- 派手な動的演出

### Background
- MASS は本デザイン研究のために作成した架空美術館であり、実在の機関ではない
- `design-art-gallery-institutional` リポジトリ予定
- art-gallery シリーズ第4作（非営利・公共軸）

---

## 2. Persona

| 属性 | 詳細 |
|------|------|
| 年齢 | 18–70代（幅広い） |
| 主要層 | 大学生・研究者・教員、家族連れ、観光客、シニア会員 |
| 動機 | 教育、研究、知的好奇心、家族レジャー、メンバーシップ更新 |
| 共鳴する価値 | 学術的正確性、アクセシビリティ、ミッション、コレクション公開性、教育プログラム |
| 嫌うもの | 商業的すぎる訴求、価格優先表示、不必要な視覚効果、複雑なナビゲーション |
| 情報源 | 学術論文、museum newsletter、新聞文化欄、教員推薦、SNS（公式アカウント） |
| アクセシビリティ要求 | 高（視覚障害者対応、多言語、スクリーンリーダー対応必須） |

---

## 3. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 一般来館者 | 現在の展覧会・開館時間・チケット情報をすぐ見つけたい | 来館計画が立てられる |
| US-02 | 研究者 | コレクションを作家・年代・素材で検索したい | 論文・調査に活用できる |
| US-03 | 大学生 | 教育プログラム・学割・インターンシップ情報を知りたい | 参加判断ができる |
| US-04 | 教員 | 学校団体向けプログラムを把握したい | 校外学習を企画できる |
| US-05 | メンバー | 会員プログラム・優先入場・限定イベントを知りたい | 会員継続価値を判断できる |
| US-06 | 海外来訪者 | 多言語UIで情報を得たい（EN / JA / ES / ZH 等） | 母語で正確に理解できる |

---

## 4. Functional Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | トップユーティリティバー：開館状況 LIVE バッジ・チケットCTA・言語切替 | P0 |
| FR-02 | ナビ：6カテゴリ (Visit / Exhibitions / Collection / Learn / Membership / About) | P0 |
| FR-03 | ヒーロー：現在展覧会のフルブリード画像 + サイドバー脚注メタ（作家、期間、curator） | P0 |
| FR-04 | Exhibitions セクション：3枚カード（current / upcoming / past）、各カードに脚注式インデックス | P0 |
| FR-05 | Collection セクション：6作品グリッド + サイドバーに分類タグ（year / medium / movement） | P0 |
| FR-06 | Visit ストリップ：開館時間・住所・地図リンク・Today/Tomorrow 状態表示 | P0 |
| FR-07 | Mission Statement セクション：大型引用・館長署名・設立年 | P1 |
| FR-08 | Learn セクション：3プログラム（K-12 / University / Public Program）リンク | P1 |
| FR-09 | Membership セクション：3階層プラン（Individual / Family / Patron）比較 | P1 |
| FR-10 | フッター：完全サイトマップ・accessibility statement・newsletter・SNS | P0 |
| FR-11 | 多言語切替 UI（EN / JA / ES / ZH ダミー切替、実装は EN/JA のみ） | P0 |
| FR-12 | スキップリンク（Skip to main content）・focus visible 強化 | P0 |
| FR-13 | モバイル対応（375px基準、ナビをハンバーガーに） | P0 |
| FR-14 | サイドバー脚注がモバイルでは下に折り畳まれる | P0 |

---

## 5. Design System

### Color Palette
```css
--bg:        #FAF7F0;   /* warm cream, 紙的だが institutional 寄り */
--bg-sub:    #F2EEE3;   /* やや深いクリーム */
--bg-deep:   #1A1A1A;   /* ダークセクション (Mission) */
--fg:        #181818;   /* 印刷インク黒 */
--fg-muted:  #5A5A56;   /* 副次テキスト */
--fg-light:  #989088;   /* キャプション・脚注番号 */
--border:    #D4CFC2;   /* サイドバー罫線 */
--accent:    #DD1A21;   /* Whitney red、ミッション・LIVE バッジ */
--accent-2:  #1A4A8E;   /* インスティテューショナル ブルー、リンク */
```

### Typography
```css
--font-display: 'Söhne Breit', 'Founders Grotesk', 'Helvetica Neue', sans-serif;
--font-sans:    'Söhne', 'Inter', -apple-system, sans-serif;
--font-serif:   'EB Garamond', 'Garamond', Georgia, serif;  /* 引用・脚注 */
```
- Söhne / Söhne Breit は商用（Klim Type Foundry）→ Google Fonts 代替: **Inter Tight** + **Inter**
- EB Garamond は Google Fonts で取得可
- Display サイズ: clamp(2.8rem, 6.5vw, 6.5rem)、wght 600、letter-spacing -0.01em
- Body サイズ: 16px / line-height 1.65（読解向け、商業より長い行送り）
- Caption / 脚注: 13px / serif italic / line-height 1.5
- ナビ: 13px / sans uppercase / letter-spacing 0.08em

### Spacing
```css
--space-xl:   clamp(5rem, 10vw, 9rem);
--space-md:   2rem;
--space-sm:   1rem;
--sidebar-w:  280px;            /* デスクトップサイドバー幅 */
--gutter:     clamp(1rem, 3vw, 2.5rem);
```

### Layout Grid
- メインコンテンツ: 12col grid、`grid-template-columns: 280px 1fr` （サイドバー左固定）
- 厳密整列、museum の壁の額装的均等性
- 余白は institutional 規範（NORE より詰める、HALF より広い）

### Motion
```css
--ease: cubic-bezier(0.22, 1, 0.36, 1);
/* loader: なし（institutional は速度を重視） */
/* hero: fade-in 0.6s のみ */
/* reveal: opacity + translateY 16px → 0, 0.7s */
/* nav: bg fade on scroll, 0.3s */
/* language switcher: dropdown 0.2s */
/* near-zero motion philosophy */
```

### Imagery
- 展覧会写真: installation view、来館者の写り込みOK（公共性の演出）
- 作品画像: museum-grade、サイドキャプション必須
- 教育プログラム写真: 子供・学生・教員、人物中心
- 館長ポートレート: モノクロまたは控えめなカラー

---

## 6. Architecture

```
index.html
├── .skip-link           # Skip to main content
├── .util-bar            # 開館状況 LIVE | チケット | 言語切替
├── nav                  # 6カテゴリ、scroll で sticky
├── .hero
│   ├── .hero-img        # フルブリード installation view
│   ├── .hero-meta       # サイドバー脚注メタ (作家|期間|キュレーター)
│   └── .hero-title      # 大型タイトル + サブタイトル
├── .section#exhibitions # 3カード (Now / Next / Past)
│   ├── .ex-card
│   │   ├── .ex-num      # "01" 脚注番号
│   │   ├── .ex-img
│   │   └── .ex-meta     # title, dates, curator
├── .section#collection  # 6作品 + サイドバー分類
│   ├── .sidebar         # year / medium / movement タグ
│   └── .work-grid       # 2x3 grid
├── .section#visit       # 開館時間・住所・地図リンク
├── .section#mission     # ダーク反転、大型引用、館長署名
├── .section#learn       # 3プログラムカード
├── .section#membership  # 3プラン比較テーブル
└── footer               # 完全サイトマップ・a11y・newsletter
```

---

## 7. Key Design Decisions

| Decision | Chosen | Rationale |
|----------|--------|-----------|
| テーマ | Light / warm cream | 紙質感だが zine 寄りでなく institutional warmth |
| Display font | Inter Tight 600（Söhne Breit 代替） | 商業ギャラリーDidoneを避け、機関的中立性 |
| Body font | Inter 16px / line-height 1.65 | 長文読解、論文的密度 |
| 引用 / 脚注 | EB Garamond italic | 学術書文法の Web 翻訳 |
| アクセント | Whitney red #DD1A21 | 美術館アイデンティティとして強い、商業ピンクと差別化 |
| リンク色 | institutional blue #1A4A8E | 古典的Webリンク、学術論文的 |
| レイアウト | 280px サイドバー + 1fr メイン | 脚注式メタ、研究者向け情報密度 |
| ナビ | 6カテゴリ常時表示 | 情報量が多くてもメガメニュー回避、平等な可視性 |
| 多言語 | UI 切替前提 | 公共性 = アクセス権、英語独占の拒否 |
| ミッション | ダーク反転セクション | 物語の中心、商業セクションから格差をつける |
| アニメーション | near-zero | パフォーマンス + a11y + 学術的trustworthiness |
| チケット | 外部リンクのみ | EC は本サイトの責務でない、信頼ある外部に委譲 |
| Footer | フルサイトマップ | a11y + SEO + institutional 慣習 |
| Skip link | 必須 | 機関サイトの最低限要件 |

---

## 8. Layout Reference

### Hero (Desktop)
```
┌──────────────────────────────────────────────────────────────┐
│ ● OPEN until 18:00     Buy Tickets ↗     EN / JA / ES / ZH  │  ← util bar
├──────────────────────────────────────────────────────────────┤
│ MASS    Visit  Exhibitions  Collection  Learn  Membership... │  ← nav (6)
├──────────────────────────────────────────────────────────────┤
│  01.    ┌─────────────────────────────────────────────────┐  │
│  ──     │                                                 │  │
│  Now    │       [ INSTALLATION VIEW, full-bleed ]         │  │
│  ──     │                                                 │  │
│  Anna   └─────────────────────────────────────────────────┘  │
│  Marlowe                                                     │  ← sidebar meta
│  ──     "After the Verb"                                    │
│  Apr 8 — Aug 24, 2026                                       │  ← title section
│  ──     Curated by R. Kobayashi                             │
│  Floor 3                                                     │
└──────────────────────────────────────────────────────────────┘
```

### Collection (Desktop)
```
┌──────────────────────────────────────────────────────────────┐
│ COLLECTION                                                   │
├─────────────┬────────────────────────────────────────────────┤
│ BY YEAR     │  ┌──────┐ ┌──────┐ ┌──────┐                 │
│  1960s (24) │  │ ART  │ │ ART  │ │ ART  │                 │
│  1970s (38) │  └──────┘ └──────┘ └──────┘                 │
│  ...        │  ┌──────┐ ┌──────┐ ┌──────┐                 │
│             │  │ ART  │ │ ART  │ │ ART  │                 │
│ BY MEDIUM   │  └──────┘ └──────┘ └──────┘                 │
│  Painting   │                                              │
│  Sculpture  │  View all 1,284 works →                      │
│  ...        │                                              │
└─────────────┴────────────────────────────────────────────────┘
```

---

## 9. Accessibility

| 項目 | 実装 |
|------|------|
| コントラスト比 | fg #181818 on bg #FAF7F0 = 15.8:1 (AAA) |
| Skip link | ページ最上部、Tab 押下で可視化 |
| キーボード操作 | 全要素 tab 可、focus-visible で #DD1A21 太枠 |
| スクリーンリーダー | 全画像 alt、SVG aria-label、ARIA landmark 適切 |
| 多言語 | `<html lang>` 切替、`hreflang` 属性 |
| フォントサイズ | px ではなく rem 基本、ユーザー設定尊重 |
| 動き | near-zero、prefers-reduced-motion で全アニメ無効化 |
| 色のみで情報伝達しない | LIVE バッジ ● は色 + テキスト両方 |
| 多重ナビゲーション | Top nav + footer sitemap + breadcrumb |
| WCAG | WCAG 2.2 AA 準拠目標 |

---

## 10. Tech & Deploy

- 単一 `index.html`、CSS Custom Properties、Vanilla JS
- フォント: Google Fonts CDN（Inter + Inter Tight + EB Garamond）
- 画像: 静的配置 + Unsplash CDN（museum installation 風）
- 多言語: data-lang 属性切替 (EN/JA のみ実装、ES/ZH はダミー表示)
- デプロイ: GitHub Pages, `design-art-gallery-institutional` リポジトリ
- カスタムドメイン: `design.art-gallery-institutional.riumu.net` 予定

---

## 11. Inspiration & References

- moma.org — 教育プログラム前面化、強いカラーシステム
- tate.org.uk — エディトリアル長文、コレクション検索の深さ
- whitney.org — Whitney red の象徴的使用、上品な編集
- guggenheim.org — installation 写真の使い方
- walkerart.org — ミニマル institutional design の到達点
- newmuseum.org — 商業ギャラリーと institutional の中間

MASS は上記から「**サイドバー脚注 + Whitney red + 多言語前提 + a11y first + ミッション主導**」を抽出した架空の機関。商業3作 (NORE / HALF / HEX) との差別化を a11y と公共性で実現。
