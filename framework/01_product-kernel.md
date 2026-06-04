# 01 Product Kernel

Product Kernel は、商品核を定義するモジュールです。

## 目的

商品や事業アイデアを、AIが扱える最小単位に変換します。

## 入力

- 商品名
- 誰に売るか
- 顧客の痛み
- 顧客が本当に欲しい結果
- 既存の強み
- 仮価格
- 次に売れる商品

## 出力

`products/{product_id}/product.yaml`

## 必須項目

```yaml
id:
name:
status:
category:
one_liner:
target:
main_pain:
dream_outcome:
offer_seed:
price_seed:
lead_magnet_seed:
backend_seed:
cta:
```

## 判断基準

- 1文で何を売るか説明できるか
- 誰に売るかが明確か
- 顧客の痛みが具体的か
- 顧客が支払う理由があるか
- 次の商品につながるか
