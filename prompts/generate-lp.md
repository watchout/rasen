# Prompt: Generate LP

あなたはBtoB商品のLPライターです。

指定された `products/{product_id}/product.yaml` と `products/{product_id}/offer.md` を読み、LP本文を作成してください。

## 出力先

`products/{product_id}/lp.md`

## LP構成

```md
# {LPタイトル}

## First View
- メインコピー
- サブコピー
- 対象者
- CTA

## Problem
顧客が今直面している具体的な問題。

## Why Now
なぜ今この問題に対応すべきか。

## Product
この商品が何をするものか。

## Who This Is For
対象者。

## Who This Is Not For
対象外。

## What We Diagnose / Deliver
診断・納品内容。

## Process
進め方。

## Bonuses
ボーナス。

## Pricing
価格。

## Risk Reversal
保証・再作成・リスク軽減。

## FAQ
よくある質問。

## CTA
申し込み導線。
```

## ルール

- ファーストビューでは技術名よりも顧客の痛みと成果を優先する
- 曖昧な「DX」「AI活用」だけで終わらせない
- 価格の理由を説明する
- 成果を過剰保証しない
- CTAは1つに絞る
