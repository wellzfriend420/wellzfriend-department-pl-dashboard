# Department PL Dashboard

会計試算表を正規化して貼り付け、部門別PL、前月・前年同月比較、利益率、経営グラフを生成するMVPです。親テンプレートの現行版は `v0.2` です。

## WFS Status

**Current Status: Candidate**

このシステムはWellzFriend Standard策定のベースモデルです。

運用しながら改善し、正式版WFSへ反映します。

## 正本

- 利用成果物: Google DriveのGoogleスプレッドシート
- 設計・検証・変更履歴: 本リポジトリ
- 業務データ: 本リポジトリへ保存しない
- テストデータ: `samples/` の合成データのみ

## cloneの位置付け

このリポジトリのcloneは、SSD上で設計・テスト・AI引継ぎ資料を保守する担当者向けです。cloneしただけではGoogleスプレッドシート本体は作成されず、日常運用も開始されません。

実運用では、Google Driveの `Templates` にある親テンプレートをコピーし、`Customers/<会社名または案件名>` に保存して使用します。初めて導入する場合は [SETUP.md](SETUP.md) の手順に従ってください。

## Google Sheets

- Template: `TPL_部門別損益ダッシュボード_v0.2`
- Spreadsheet ID: `1pY1Q8tuJWJBq25zL-PKuOmygZ50XYffnJ6cRPKiym-Q`
- URL: https://docs.google.com/spreadsheets/d/1pY1Q8tuJWJBq25zL-PKuOmygZ50XYffnJ6cRPKiym-Q/edit

## 文書

- `SETUP.md`: cloneから実運用開始までの手順
- `README_AI.md`: AI向け引継ぎ設計書
- `SYSTEM_ARCHITECTURE.md`: システム構成
- `DATABASE.md`: データ構造
- `CHANGELOG.md`: 更新履歴
- `TODO.md`: 改善候補
- `tests/TEST_CASES.md`: 検証仕様と結果
- `docs/WFS_CANDIDATES.md`: 標準化候補

## GitHubに保存するもの

- README、README_AI、セットアップ手順
- システム設計、データ構造、スプレッドシート仕様
- テストケースと個人情報を含まない合成サンプル
- 変更履歴、改善候補、WFS候補
- 将来Apps Scriptを採用した場合のソースコード

現時点ではApps Scriptを使用しておらず、Apps Scriptのソースコードもありません。Googleスプレッドシート本体、顧客データ、日々の運用データはGitHubへ保存しません。

## 原則

`DATA → CALC → REPORT / DASHBOARD` の依存方向を守ります。実データ、認証情報、APIキー、個人情報はコミットしません。
