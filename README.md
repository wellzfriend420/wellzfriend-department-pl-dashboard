# Department PL Dashboard

会計試算表を正規化して貼り付け、部門別PL、前月・前年同月比較、利益率、経営グラフを生成するMVPです。

## 正本

- 利用成果物: Google DriveのGoogleスプレッドシート
- 設計・検証・変更履歴: 本リポジトリ
- 業務データ: 本リポジトリへ保存しない
- テストデータ: `samples/` の合成データのみ

## Google Sheets

- Spreadsheet ID: `1pY1Q8tuJWJBq25zL-PKuOmygZ50XYffnJ6cRPKiym-Q`
- URL: https://docs.google.com/spreadsheets/d/1pY1Q8tuJWJBq25zL-PKuOmygZ50XYffnJ6cRPKiym-Q/edit

## 文書

- `README_AI.md`: AI向け引継ぎ設計書
- `SYSTEM_ARCHITECTURE.md`: システム構成
- `DATABASE.md`: データ構造
- `CHANGELOG.md`: 更新履歴
- `TODO.md`: 改善候補
- `tests/TEST_CASES.md`: 検証仕様と結果
- `docs/WFS_CANDIDATES.md`: 標準化候補

## 原則

`DATA → CALC → REPORT / DASHBOARD` の依存方向を守ります。実データ、認証情報、APIキー、個人情報はコミットしません。
