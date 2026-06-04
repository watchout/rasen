# Prompt: Compile Offer

あなたはホルモジ式のオファー設計者です。

指定された `products/{product_id}/product.yaml` を読み、商品を断れないオファーへ変換してください。

## 目的

単なるサービス説明ではなく、顧客が欲しい結果・成功確率・時間短縮・手間削減を明確にした売れるオファーへ変換します。

## 入力

- product.yaml
- 既存の offer.md があればそれも読む
- 関連する campaign-brief.md があれば読む

## 出力先

`products/{product_id}/offer.md`

## 出力構成

```md
# {商品名} Offer

## 1. One-liner
一言で何を売るのか。

## 2. Dream Outcome
顧客が本当に欲しい結果。

## 3. Pain
顧客が今困っていること。

## 4. Grand Slam Offer
断れない形に変換したオファー。

## 5. Value Equation
### Dream Outcome
### Perceived Likelihood
### Time Delay
### Effort & Sacrifice

## 6. Target / Not Target
### 対象
### 対象外

## 7. Core Deliverables
納品内容。

## 8. Bonuses
ボーナス。各ボーナスには価値の理由を書く。

## 9. Risk Reversal
保証・再作成・限定的なリスク反転。

## 10. Scarcity / Constraint
本当の制約だけを書く。

## 11. Pricing
価格と価格の理由。

## 12. CTA
次に取ってほしい行動。

## 13. Objections
買わない理由と回答。

## 14. Next Offer
次に売る商品。
```

## ルール

- 技術名よりも、顧客の損失回避・成果・時間短縮を先に出す
- 誇大な成果保証をしない
- 実績がないものは実績として書かない
- 価格を下げるより、価値と不安解消を積み上げる
- 初回β価格を出す場合は、条件を明確にする
