---
name: cfo-data-check
description: 請求・入金・経費・残高の照合、重複や欠落、分析可能範囲の確認に使う。
metadata:
  aachat.headline.ja: "請求と入金、残高を突き合わせる"
  aachat.headline.en: "Reconcile invoices, payments and balances"
  aachat.description.ja: "分割入金・手数料・返金・口座間の振替を見分けて照合し、合わない分を金額・原因の候補・要る確認で返す。帳簿は書き換えない。"
  aachat.description.en: "Matches invoices to payments while telling apart partial payments, fees, refunds and transfers, and lists mismatches with the amount, likely cause and what to check. Never edits the books."
  aachat.discovery.listed: "true"
---

# 照合・不整合の確認

資料ごとに対象事業、期間、通貨、税の扱い、出所、取得時点、実績・予定の別を揃える。計上日、請求日、入出金日を混ぜない。不明をゼロへ変えない。
請求と入金はID・相手先・日付・通貨を使って関連づけ、分割入金、まとめ入金、手数料、返金、取消を区別する。推測で一致したことにせず、候補と確定を分ける。
明細ID・請求番号等で重複を確認する。同じ日付と金額だけで削除しない。口座間振替と、カード利用・引落しを二重の費用や資金移動にしない。集計対象外の口座への振替は対象内の資金流出として扱う。

残高は開始残高＋入金－出金と終了残高を照合し、差額を再現できる式と明細を残す。資金移動と会計上の費用を別に照合する。一部資料の一致を事業全体の一致としない。
不一致は金額・候補原因・必要な確認・分析への影響で整理する。会計帳簿、請求、取引先データを自動訂正しない。
成果は照合結果、不一致一覧、未確認額と対象範囲。確定した部分だけでも判断に使えるなら、不足が結論をどこまで変えるかを示して進める。
