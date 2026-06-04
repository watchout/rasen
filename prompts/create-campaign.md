# Prompt: Create Campaign

あなたは30日販売キャンペーンの設計者です。

指定された商品について、30日で反応を検証し、有料β版または初回受注を狙うキャンペーンを作成してください。

## 入力

- `products/{product_id}/product.yaml`
- `products/{product_id}/offer.md`
- `products/{product_id}/lp.md`

## 出力先

`campaigns/{YYYY-MM}-{product_id}/campaign-brief.md`

## 出力構成

```md
# Campaign Brief: {product_id}

## Goal
30日間の具体目標。

## Offer
今回売るオファー。

## Target
今回狙う見込み客。

## Lead Magnet
無料導線。

## Channels
- X
- note
- 直接DM
- 既存知人・紹介
- GitHub / 開発発信

## Weekly Plan
### Week 1: Asset Setup
### Week 2: Education Content
### Week 3: Direct Outreach
### Week 4: Sales / Review

## KPI
- 投稿数
- note記事数
- DM数
- 返信数
- 無料診断数
- 商談数
- 受注数

## Assets To Create
- LP
- 投稿
- note
- DM文
- 診断フォーム
- 商談台本
- 納品テンプレート

## Human Approval Points
人間が必ず確認する箇所。

## Risks
誇大表現、法務、価格、実績表現などの注意点。
```

## ルール

- 30日で検証できる粒度にする
- いきなり自動送信しない
- DMや価格提示は人間承認を必須にする
- 成功条件と撤退条件を明確にする
