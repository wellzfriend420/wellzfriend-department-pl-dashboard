# System Architecture

```text
会計CSV / 試算表
       |
       v
DATA（正規化明細）---- SETTINGS（分類マスタ）
       |
       v
CALC（月次・累計・前年同期・部門比較・科目内訳）
       |
       v
REPORT（部門別累計PLの参照表示）
       |
       v
DASHBOARD（経営判断用の参照表示）
```

## 境界

- DATA: 利用者の唯一の定常入力先
- SETTINGS: 会社差異、部門、科目分類
- CALC: すべての集計を一元管理する唯一の計算層
- REPORT: 部門別累計PLと前年同期累計比較を表示する経営判断層
- DASHBOARD: 部門別累計の成長性・収益性を要約する経営判断層

REPORTでDATAを直接集計せず、DASHBOARDで再集計しない。表示層の式は参照・検索・表示整形に限定する。

## Web移行対応

| Sheets | Webアプリ候補 |
|---|---|
| DATA | journal_entries / import API |
| SETTINGS | company、department、account_mapping |
| CALC | aggregation service / SQL view |
| REPORT | PL report endpoint |
| DASHBOARD | management UI |

## 保存責務

- Google Sheets実体: Google Drive
- 設計・コード・テスト: 個別GitHub
- 共通標準・台帳: WellzFriend_OS
- 日常業務データ: 将来の会社統合DB

本プロジェクトの知見は `docs/WFS_CANDIDATES.md` で検証後、WellzFriend_OSへ昇格判定する。
