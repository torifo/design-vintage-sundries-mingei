[English](#english) | [日本語](#japanese)

---

<a id="english"></a>

# TSUCHI to ITO — design-vintage-sundries-mingei

> **"What the hand remembers."**

A design study exploring a fictional mingei (Japanese folk-craft) sundries shop — targeting **a 34-year-old freelance editor living in a Kominka (old folk house)** who reveres Yanagi Soetsu's philosophy of *yo no bi* (the beauty of usefulness) and wants tools that age with daily use.

TSUCHI to ITO is a fictional shop created for this design study. It is not a real shop, store, or product.

## Overview

| | |
|---|---|
| **Brand** | TSUCHI to ITO (土と糸) |
| **Persona** | mingei (Folk craft) |
| **Live Site (planned)** | `design.vintage-sundries-mingei.riumu.net` |

## Design Concept

- **Color**: Indigo `#1d3a5f` × iron-rust brown `#7a4a2d` × unbleached linen `#f3ecdc` × vermilion seal `#a8412c`
- **Typography**: Shippori Mincho B1 (display) × Noto Serif JP (body) × Sawarabi Mincho (kana)
- **Aesthetic**: Yanagi Soetsu's mingei movement × washi paper texture × vertical-rl typesetting
- **UX**: Vertical-rl pull-quotes, seal-stamped store note, 4 articles ("yomimono"), and 4 "shop principles" in dark-inverted block
- **Texture**: SVG washi noise with `mix-blend-mode: multiply`

## Tech Stack

- Pure HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN (Shippori Mincho B1 + Noto Serif JP + Sawarabi Mincho)
- No framework, no build step — GitHub Pages ready

## Spec

See [spec.md](./spec.md) for the full design specification.

## Install as a skill / スキルとして導入

This repo ships a cross-agent **`SKILL.md`** (open standard) usable by both Claude Code and Codex CLI as a design-reference skill. Link the repo into the agent's skills directory:

このリポジトリは Claude Code / Codex CLI 共通の **`SKILL.md`**（オープン標準）を同梱し、デザイン参照スキルとして使えます。

```bash
# Claude Code
ln -s "$(pwd)" ~/.claude/skills/design-vintage-sundries-mingei
# Codex CLI
ln -s "$(pwd)" ~/.codex/skills/design-vintage-sundries-mingei
```

Restart the agent; it is matched automatically by the skill's `description` (skill name: `design-vintage-sundries-mingei`). / エージェント再起動後、`description` に基づき自動マッチします。

## Part of

This repository is one of four design studies under the **vintage-sundries persona series**:

| Persona | Brand | Aesthetic |
|---------|-------|-----------|
| **mingei** | TSUCHI to ITO | Folk craft, yo no bi, washi |
| showa-retro | KISSA MIKAZUKI | Showa kissaten, city pop |
| zakka | hibi-zakka | Natural wa-modern, handcraft |
| kottou | IKKOKU | Edo antiques, museum-grade |

Navigator: [vintage-sundries](../README.md)

---

<a id="japanese"></a>

# 土と糸 — design-vintage-sundries-mingei（日本語）

> **「手が憶えてくれる道具を」**

ヴィンテージ雑貨 ・ デザイン研究シリーズの民藝ペルソナ。**34歳・古民家暮らしのフリーランス編集者**——柳宗悦の「用の美」を信条にし、日々の暮らしと共に育つ道具を求める層——に特化した架空店舗「土と糸（TSUCHI to ITO）」のサイトです。

土と糸は本デザイン研究のために作成した架空店舗です。実在の店舗・商品ではありません。

## 概要

| | |
|---|---|
| **ブランド** | 土と糸（TSUCHI to ITO） |
| **ペルソナ** | mingei（民藝） |
| **公開URL（予定）** | `design.vintage-sundries-mingei.riumu.net` |

## デザインコンセプト

- **カラー**: 紺藍 × 鉄錆 × 生成り × 朱印（アクセント）
- **フォント**: Shippori Mincho B1（見出し）× Noto Serif JP（本文）× Sawarabi Mincho（かな）
- **世界観**: 柳宗悦的民藝運動 × 和紙テクスチャ × 縦書き混在
- **UX**: 縦書き引用、店主一筆（朱印付き）、読みもの4本、店の信条4条（ダーク反転）
- **テクスチャ**: SVG 和紙ノイズ＋暖色 multiply

## 技術

- 純粋なHTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN（Shippori Mincho B1 + Noto Serif JP + Sawarabi Mincho）
- ビルド不要で GitHub Pages 対応

## 仕様書

詳細は [spec.md](./spec.md) を参照。デザイン判断の経緯は [DESIGN_LEARNINGS.md](./DESIGN_LEARNINGS.md) に。

## シリーズ

ヴィンテージ雑貨 ・ ペルソナシリーズ4作のうち1作。
ナビゲーターページ: [vintage-sundries](../README.md)
