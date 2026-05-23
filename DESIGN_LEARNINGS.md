# MASS Design Learnings

## 目的

institutionalペルソナは、学生・研究者・家族連れ・一般来館者という年齢層も背景も極端に幅広い来訪者。コマーシャルな美意識を持ち込むと、公的機関としての説明責任が果たせない。MASSでは、ミッションを最優先に据え、多言語UI・WCAG 2.2 AA 準拠・サイドバー脚注という学術エディトリアルの形式を採用した。

この美術館は架空ブランドであり、実在の機関・作家・作品ではない。

## 設計したこと

- 6カテゴリの常設ナビ（Visit / Exhibitions / Collection / Learn / Membership / About）。観光客の動線（Visit）と学術利用（Collection）の両立を最上位に置いた。
- 4言語スイッチャー（EN / JA / ES / ZH）をヘッダーに常設。北米都市部の公共美術館を想定した。
- ヒーローとコレクションにはサイドバーメタを併走させ、研究者がメタデータを最短で参照できる構造にした。
- Mission をダーク反転 blockquote として配置。商業的なCTAではなく、機関の思想を画面の中央に据えた。
- skip-link、`prefers-reduced-motion`、コントラスト比、`aria-label` を全要素で点検した。

## CSS

主要なCSS判断:

```css
:root {
  --cream: #faf7f0;        /* warm cream paper */
  --ink: #181818;
  --red: #dd1a21;           /* mission/LIVE accent only */
  --blue: #1a4a8e;          /* institutional link blue */
  --font-display: 'Inter Tight', 'Söhne Breit', sans-serif;
  --font-body: 'Inter', sans-serif;
  --font-serif: 'EB Garamond', 'Noto Serif JP', serif;
}

/* skip link, visible on focus */
.skip-link {
  position: absolute;
  left: -999em;
}
.skip-link:focus {
  left: 1rem; top: 1rem;
  background: var(--ink);
  color: var(--cream);
  padding: .8em 1.4em;
  z-index: 100;
}

/* sidebar footnote layout */
.editorial {
  display: grid;
  grid-template-columns: 1fr 18rem;
  gap: clamp(2rem, 5vw, 5rem);
}
.editorial aside.footnotes {
  font-family: var(--font-serif);
  font-size: .82rem;
  border-left: 2px solid var(--ink);
  padding-left: 1.5rem;
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation-duration: 0!important; transition: none!important; }
}
```

赤は LIVE バッジとミッション関連のみ、青はリンクのみ、と機能割り当てを厳格化。色のみで情報を伝えないという原則を CSS の階段で担保した。

## アニメーション

- 動きはミニマル。reveal は y軸 6px、`cubic-bezier(.2,.7,.2,1)` で1回のみ。
- `prefers-reduced-motion` 適用時はすべての trans/anim を 0 にする。
- LIVE バッジの脈動はWCAGに照らして 3Hz 未満に厳守。

## フォント

- Display: `Inter Tight 600`（Söhne Breit 代替として）
- Body: `Inter`
- Quotes / footnotes: `EB Garamond`

学術サイトに本文セリフを採用するか散々悩んだが、長文の可読性とアクセシビリティの両立で Inter を選んだ。引用と注はセリフに切り替え、エディトリアルの呼吸を保った。

## ボタン

ボタンは「機能のラベル」として作る。

- 主要 CTA は塗りボタン1色（ink）、二次 CTA は枠線のみ。
- 「Plan your visit」「Become a member」は機能語で書き、感情に訴える文言を避けた。
- フォーカスリングはブラウザ既定を尊重しつつ、`outline-offset` のみ調整。

## UI/UX

- Mission セクションをトップに置き、説明責任を可視化。
- Exhibitions には作品リスト・学芸員・期間・無料/有料を構造化して掲載。
- Visit にはチケット・アクセス・バリアフリーを必ず併記。
- Membership は段階別表で、寄付ベースの語彙（gift / support）を採用。

## レイアウト

センターコラム+右サイドバー脚注、というスタイルガイド誌風の構造を基本とした。サイドバーには制作年・寸法・コレクション番号・素材を学術カードのフォーマットで並べている。

人物が映ったインスタレーション写真をヒーローに採用し、「無人のホワイトキューブ」を回避した。MASSは公共空間であり、観客の身体性を画面に残すことが思想と一致する。
