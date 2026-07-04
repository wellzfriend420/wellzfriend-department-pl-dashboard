# System Architecture

```text
会計CSV / 試算表
       |
       v
DATA（正規化明細）
       |
       v
SETTINGS（マスタ）----> CALC（月次・部門別集計）
                              |
                    +---------+---------+
                    v                   v
                 REPORT             DASHBOARD
```

## 境界

- DATA: 利用者の唯一の定常入力先
- SETTINGS: 会社差異、部門、科目分類
- CALC: 表示形式を持たない集計層
- REPORT / DASHBOARD: 計算ロジックを重複させない表示層

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
