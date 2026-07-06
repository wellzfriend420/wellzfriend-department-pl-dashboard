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
- REPORT: PL集計はCALC、製造経費の勘定科目別内訳はDATAを参照する
- REPORTの当期累計: SETTINGSの会計年度開始月から表示月まで
- REPORTの前年同期累計: 当期累計期間の12か月前

## Rebuild policy

現MVPはGoogle Sheetsが利用実体です。自動再構築コードは、実運用で入力形式と科目分類が安定した後に追加します。それまでは本仕様とREADME_AIを正本として変更差分を管理します。

実運用ファイルはGoogle Driveの親テンプレートからコピーします。cloneしたリポジトリからGoogleスプレッドシートを自動生成する機能はありません。
