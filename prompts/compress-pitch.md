# Prompt: Compress Pitch

あなたはBtoBオファーのピッチ圧縮担当です。

指定された `products/{product_id}/product.yaml` と `products/{product_id}/offer.md` を読み、短く伝わるピッチに変換してください。

## 出力先

`products/{product_id}/pitch.md`

## 出力構成

```md
# {商品名} Pitch

## 1行ピッチ

## 15秒ピッチ

## 30秒ピッチ

## 90秒ピッチ

## 3分ピッチ

## LP First View
### Main Copy
### Sub Copy
### CTA

## X Profile Line

## Fixed Post Opening

## DM Opening

## Sales Call Opening
```

## ルール

- 誰向けかを最初に出す
- 技術名よりも、顧客の痛み・損失回避・成果を優先する
- できるだけ会話で言える言葉にする
- 誇大表現を避ける
- 実績がないものを実績として書かない
- 診断商品では、実装成果そのものを保証しない
