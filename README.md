# らせん / Rasen

らせんは、複数プロダクトをホルモジ式の売上導線に変換し、発信・商談・納品・改善を繰り返しながら事業を上昇させるための Growth OS です。

このリポジトリは、IYASAKA の複数事業を横断して、商品定義・オファー設計・LP・無料診断・発信・商談台本・納品テンプレート・改善ログを GitHub 上で管理するための場所です。

## 目的

- 複数プロダクトを同じ型で整理する
- 売るべき順番をスコアリングする
- ホルモジ式で魅力的なオファーへ変換する
- 技術起点ではなく、必要起点で商品を作る
- LP、投稿、診断フォーム、営業資料、納品物を生成する
- Codex / Claude Code / Aun Stack / shirube と連携しやすい形にする
- 反応・商談・受注・失注理由を蓄積して改善する

## らせんの基本思想

同じ場所を回っているように見えて、毎回一段上がる。

商品 → オファー → 発信 → リード → 商談 → 受注 → 納品 → 事例化 → 改善 → 次の商品、という循環を回しながら、事業全体を上昇させる。

ただし、Rasen は「すごいもの」を作るためだけの仕組みではない。
必要とされるものを、必要としている人に、届く形で作るための Growth OS として扱う。

## 最初の運用対象

第一号の深掘り対象は、以下の商品です。

- AI案件 受注前リスク診断

その他のプロダクトは、まず薄い product.yaml として登録し、優先順位スコアリングの対象にします。

## ディレクトリ構成

```text
framework/   らせんのモジュール定義と横断原則
products/    各プロダクトの定義・オファー・LP・営業導線
prompts/     Codex / Claude Code に渡す運用プロンプト
campaigns/   30日単位の販売キャンペーン
reports/     週次レビュー、数値、学び、改善ログ
```

## 横断原則

- `framework/00_iyasaka-philosophy.md`: 相手を勝たせながら売上を上げる判断姿勢
- `framework/00a_need-first-principle.md`: AIや型から入らず、相手の必要から作る判断軸
- `framework/10_outward-mindset-guard.md`: 顧客・取引先・協業先への向き合い方を確認する横断チェック

## 実行モジュール

1. Product Kernel: 商品核を定義する
2. Market Lens: 市場・顧客・痛みを特定する
3. Offer Compiler: ホルモジ式でオファーに変換する
4. Asset Factory: LP・投稿・診断・営業資料を生成する
5. Lead Engine: リード獲得導線を作る
6. Sales Pipeline: 商談・提案・受注へ進める
7. Delivery System: 納品・継続課金・アップセルへつなげる
8. Feedback Loop: 数値・事例・失注理由から改善する
9. Pitch Compressor: オファーを短く伝わる言葉へ圧縮する

## 最初の使い方

1. `framework/00_iyasaka-philosophy.md` を読む
2. `framework/00a_need-first-principle.md` を読む
3. `framework/10_outward-mindset-guard.md` を読む
4. `products/index.yaml` で全プロダクトを確認する
5. `prompts/score-products.md` で今月の優先順位を出す
6. 上位プロダクトに `prompts/compile-offer.md` を適用する
7. 必要に応じて `prompts/run-need-first-check.md` で確認する
8. `prompts/create-campaign.md` で30日キャンペーンを作る
9. `reports/weekly/` に週次レビューを残す
10. 反応・失注理由・成約理由を各商品の `metrics.md` に戻す

## 原則

- まず売る。作り込みすぎない。
- ただし、作る前に誰の何を楽にするのか確認する。
- すべてのプロダクトを同時に深掘りしない。
- 全商品を薄く登録し、上位1〜3個だけ深く掘る。
- LPや投稿より先に、買う理由と買わない理由を明確にする。
- 技術の深さを、相手への敬意と実用価値に変換する。
- AIが作成し、人間が承認する。
- 実績・反応・失注理由を必ず次の改善に戻す。
