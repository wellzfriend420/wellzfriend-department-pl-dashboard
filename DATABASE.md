# Database / Data Structure

## DATA

| 項目 | 型 | 必須 | 説明 |
|---|---|---|---|
| posting_date | date | yes | 計上日 |
| department_name | string | yes | 登録部門 |
| account_name | string | yes | 科目マッピングキー |
| amount | number | yes | MVPでは収益・費用とも正数推奨 |
| memo | string | no | 摘要 |
| posting_month | date | derived | 月初日へ正規化 |
| pl_category | enum | derived | SETTINGSから取得 |

## PL区分

`売上高 / 原材料費 / 外注費 / 労務費 / 包装資材費 / 製造経費 / その他原価 / 販管費`

## 将来の配賦

元明細を変更せず、`allocation_rules` と `allocation_results` を追加する。ルールの版と適用期間を保存し、配賦前後を再現可能にする。

## 品質制約

- 未登録部門を拒否する。
- 未分類科目をエラー一覧へ出す。
- 日付・金額の欠損を拒否する。
- 将来はimport IDで重複取込を防止する。
