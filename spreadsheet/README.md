# Spreadsheet Specification

## Sheet order

1. README_AI
2. CHANGELOG
3. SETTINGS
4. DATA
5. CALC
6. DASHBOARD
7. REPORT

## Formula boundaries

- DATA A:E: input
- DATA F:G: derived month and PL category
- CALC: 36 months × `3 departments + total`
- DASHBOARD: CALCを参照する
- REPORT: 部門別の当期累計PLを主表とし、前年同期累計比較と製造経費累計内訳を表示する
- DASHBOARD: 部門別累計売上、営業利益、利益率、前年同期比を主役とする
- 月次推移グラフ: 補助情報として残し、主判断には使用しない
- 当期累計: SETTINGSの会計年度開始月から表示月まで
- 前年同期累計: 当期累計期間の12か月前

## Rebuild policy

現MVPはGoogle Sheetsが利用実体です。自動再構築コードは、実運用で入力形式と科目分類が安定した後に追加します。それまでは本仕様とREADME_AIを正本として変更差分を管理します。

実運用ファイルはGoogle Driveの親テンプレートからコピーします。cloneしたリポジトリからGoogleスプレッドシートを自動生成する機能はありません。
