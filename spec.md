# 土と糸 — vintage-sundries/mingei Spec

**Status:** Approved
**Author:** torifo
**Created:** 2026-05-23
**Updated:** 2026-05-23

---

## 1. Overview

### Problem Statement
古道具・民藝に関心のある30〜40代の生活者は、量産的なECサイトでは古道具の「気配」や「ものの履歴」が伝わらず、購買決定の手前で離脱する。柳宗悦の説いた「用の美」というキー思想と、現代のWeb UI 言語の間に橋渡しが必要である。

### Goal
民藝運動の世界観を出発点に、和紙の質感・印章・縦書き混在の組版・落ち着いた藍×鉄錆×生成りの配色で構築した架空店舗「土と糸（TSUCHI to ITO）」を実装し、古道具の Web ストアフロントが持ち得る最も静謐な形を検証する。

### Non-Goals
- 実際の在庫検索 ・ カート ・ 決済機能
- 商品写真の撮影フロー
- CMS 連携

### Background
- 土と糸は本デザイン研究のために作成した架空店舗であり、実在のギャラリー ・ 店舗 ・ 商品ではない
- `vintage-sundries/mingei` フォルダ、`design.vintage-sundries-mingei.riumu.net` 独自ドメイン予定
- 同シリーズ4作の中で「静謐 ・ 縦書き混在 ・ 明朝主体」の唯一のサイト

---

## 2. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 古民家暮らしの30代編集者（林 美咲想定） | ページを開いた瞬間に「民藝らしさ」を感じたい | 「ここで買えば暮らしと馴染む」と直感できる |
| US-02 | 同上 | 作り手の人物像を読みたい | 道具の背景を理解した上で選びたい |
| US-03 | 同上 | 店主のエッセイ（読みもの）に触れたい | 価格より前に世界観に共鳴したい |
| US-04 | 同上 | スマートフォンでもじっくり読みたい | 通勤・休日いずれでも没入できる |

### Acceptance Criteria

**US-01:**
- WHEN ページが読み込まれた THEN 縦書きキャッチコピー＋大型明朝の主題が現れる
- WHEN 表示後 THEN 和紙ノイズ＋藍×鉄錆×生成りで「印刷物のような」第一印象がある

**US-02:**
- WHEN 作り手セクションに到達した THEN 3名分の名前 ・ 工房名 ・ 経歴が読める
- WHEN 各人物の文章を読んだ THEN 道具との関係性が描写されている

**US-03:**
- WHEN 読みものセクションに到達した THEN 4本以上のエッセイが、章番号＋年月日と共に並ぶ
- WHEN タイトルを見た THEN 商業文ではなく随筆的トーンであると分かる

**US-04:**
- WHEN 375px 幅で閲覧した THEN 縦書きパーツは安全に横書きへ畳まれ、可読性を維持する

---

## 3. Functional Requirements

| ID | Requirement | Priority | Notes |
|----|-------------|----------|-------|
| FR-01 | 縦書きヒーロー文＋大型明朝主題 | P0 | writing-mode: vertical-rl |
| FR-02 | 和紙ノイズ＋暖色オーバーレイ | P0 | SVG feTurbulence multiply |
| FR-03 | 引用ブロック（柳宗悦） | P0 | 中央寄せ、出典付き |
| FR-04 | 道具棚（商品6点、SVGイラスト） | P0 | 入荷・藍・古布タグ |
| FR-05 | 作り手セクション（3名） | P0 | 工房バッジ付 |
| FR-06 | 読みもの（エッセイ4本） | P1 | 縦書き章番号 |
| FR-07 | 店の信条（4条） | P1 | ダーク反転セクション |
| FR-08 | 店の案内＋訪う一筆 | P0 | 店主印スタンプ含む |
| FR-09 | スクロールリビール（上方移動） | P1 | 移動量 20px、1.2s |
| FR-10 | ヘッダー（明朝ロゴ・ナビ） | P0 | sticky なし |
| FR-11 | モバイル対応（375px 基準） | P0 | 縦書き要素はモバイルで横書きに |

---

## 4. Architecture

```
mingei/index.html
├── <header>                       # 明朝ロゴ＋4項目ナビ
├── <section class="hero">         # 縦書き＋大型主題
├── <section class="quote">        # 柳宗悦引用
├── <section id="tana">            # 道具棚 6商品
├── <section id="tsukurite">       # 作り手 3名
├── <section id="yomu">            # 読みもの 4本
├── <section id="shinjou">         # 信条 4条（ダーク反転）
├── <section id="otonau">          # 店の案内＋店主印
└── <footer>                       # 4店舗ナビ
```

### Key Design Decisions

| Decision | Chosen | Rationale | Rejected |
|----------|--------|-----------|----------|
| テーマ | ライト（暖） | 民藝の素材感 | ダーク（骨董と被る） |
| 主書体 | Shippori Mincho B1 | 民藝書物の組版 | 游明朝（CDN無し） |
| 書字方向 | 横＋縦混在 | 暦・印章の語彙 | 全縦書き（可読性低下） |
| 装飾 | 印章＋朱の四角 | 民藝の押印文化 | スタンプ・テープ |
| アクセント | 朱（#a8412c） | 印章色 | 蛍光・派手色 |
| アニメ | 静謐な fadeup | 民藝の節度 | 強いスライド |

---

## 5. Design System

### Color Palette
```css
--ai:#1d3a5f;      /* 紺藍 */
--ai-fukai:#0f2238;
--sabi:#7a4a2d;     /* 鉄錆 */
--sabi-asa:#a86b48;
--kinari:#f3ecdc;   /* 生成り */
--washi:#ece2cf;
--sumi:#1a1714;
--kusa:#5a6b3e;
--shu:#a8412c;       /* 朱印 */
--hai:#928a7c;
```

### Typography
```css
--font-mei:'Shippori Mincho B1','Noto Serif JP',serif;     /* 見出し ・ 数字 */
--font-honbun:'Noto Serif JP',serif;                       /* 本文 */
--font-kana:'Sawarabi Mincho','Noto Serif JP',serif;       /* かな */
```

### Texture & Motion
```css
/* 和紙ノイズ */
body::before {
  background: url("...feTurbulence baseFrequency=.85...");
  mix-blend-mode: multiply;
  opacity: .55;
}

/* リビール */
@keyframes fadeup { from { opacity:0; transform: translateY(20px) } to { opacity:1; transform: none } }
.reveal { animation: fadeup 1.2s cubic-bezier(.2,.7,.2,1) both }
```

---

## 9. Testing Strategy

| Layer | Scenarios |
|-------|-----------|
| Desktop (1280px) | 縦書きヒーロー位置、商品グリッド6枚、引用中央配置 |
| Mobile (375px) | 縦書きパーツの安全な折返し、商品1カラム化 |
| アニメ | fadeup × IntersectionObserver で順次出現 |
| ホバー | 商品カードに過剰効果なし（民藝らしい節度） |
| フォント | Shippori Mincho B1 / Sawarabi Mincho 正常適用 |

---

## 10. Implementation Notes

- **縦書き**: `writing-mode: vertical-rl` を hero と章番号、エッセイ番号に限定して採用
- **和紙テクスチャ**: SVG `feTurbulence` を `position:fixed` 疑似要素に重ね、暖色チャートで合成
- **印章モチーフ**: `border:2px solid var(--shu)` + `border-radius:50%` + `transform: rotate(-8deg)` のスタンプを店主一筆に配置
- **章番号**: 「壹 ・ 貳 ・ 參 ・ 肆」の旧字を採用し、商業性ではなく書物的トーンを強調
- **モバイル対応**: 縦書きの hero-tate は `min-width:880px` 未満で表示位置を上に配し、縦長スクリーンで二段組になる

---

## 11. Open Questions

| # | Question | Status |
|---|----------|--------|
| 1 | 商品の SVG イラストを将来的に写真へ差し替えるか | Open |
| 2 | 「読みもの」を個別ページとして展開するか | Open |
| 3 | 信条セクションの ダーク反転は他ペルソナと差別化できているか | Confirmed |

---

## References

- [navigator README](../README.md)
- Font: [Shippori Mincho B1](https://fonts.google.com/specimen/Shippori+Mincho+B1), [Sawarabi Mincho](https://fonts.google.com/specimen/Sawarabi+Mincho)
- Inspiration: 日本民藝館図録 ・ 河井寛次郎記念館 ・ 柳宗悦『工藝の道』
