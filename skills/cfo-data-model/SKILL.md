---
name: cfo-data-model
description: 照合済み資料を商品・顧客・案件別の分析へ整え、分類・集計の根拠を残すときに使う。
metadata:
  aachat.headline.ja: "商品・顧客・案件別に分析できる表に整える"
  aachat.headline.en: "Shape data for analysis by product, customer and project"
  aachat.description.ja: "元資料の ID を残したまま、売上・費用・入出金・工数を分けた表にする。分類の決め方を残し、集計の前後で金額を照合する。"
  aachat.description.en: "Builds an analysis table that keeps source IDs and separates revenue, costs, cash flows and hours. Records how items were classified and checks totals before and after."
  aachat.discovery.listed: "true"
---

# 分析用データの整理

どの判断で何を比較するかに合わせ、必要な列と粒度を選ぶ。専用DBを前提にせず、既存の表・ファイル・接続先を使う。
行には元資料IDと行・取引ID、対象期間、通貨、税区分、実績・予定・仮定、計上日と入出金日、必要な商品・顧客・案件の識別子を残す。
売上、返金、費用、入出金、残高、工数は異なる指標として持つ。金額の符号と集計方法を明記し、不同通貨を換算根拠なしで合算しない。

顧客名の表記揺れや案件との対応は元の値を残して別列で管理する。不明な分類は未分類として残し、推測した分類には根拠と確認状況を付ける。固定費の配賦は基準・対象・配賦前後を残す。
集計前後の件数・金額と照合対象の総額を比べ、除外分・未分類分・差額を説明する。判断に効く未分類だけ本人に返す。
成果は分析用データ、列と分類の定義、変換手順、元資料への対応、利用可能範囲。次回更新では同じ定義で比較し、定義変更による差を実際の事業変化と分ける。
