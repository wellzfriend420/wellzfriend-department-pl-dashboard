# Spreadsheet Specification

## Sheet order

1. README_AI
2. CHANGELOG
3. SETTINGS
4. DATA
5. CALC
6. DASHBOARD
7. REPORT
8. EXECUTIVE_REPORT

## Formula boundaries

- DATA A:E: input
- DATA F:G: derived month and PL category
- CALC: 36 months × `3 departments + total`
- CALC: 月次、当期累計、前年同期累計、成長率、部門比較、製造経費科目内訳をすべて計算する
- REPORT: CALCの計算済み列をXLOOKUPで表示する。SUMIFSとDATA参照は禁止する
- DASHBOARD: REPORTおよびCALCのグラフ用出力を直接参照する。SUMIFS、XLOOKUP、DATA参照は禁止する
- DASHBOARD: 部門別累計売上、営業利益、利益率、前年同期比を主役とする
- EXECUTIVE_REPORT: CALCの計算済み結果をXLOOKUPで表示する。SUMIFSとDATA参照は禁止する
- EXECUTIVE_REPORT: A4横1枚の提出用資料とし、コメント欄・経営者メモ欄以外は表示専用とする
- 月次推移グラフ: 補助情報として残し、主判断には使用しない
- 当期累計: SETTINGSの会計年度開始月から表示月まで
- 前年同期累計: 当期累計期間の12か月前

## Rebuild policy

現MVPはGoogle Sheetsが利用実体です。自動再構築コードは、実運用で入力形式と科目分類が安定した後に追加します。それまでは本仕様とREADME_AIを正本として変更差分を管理します。

実運用ファイルはGoogle Driveの親テンプレートからコピーします。cloneしたリポジトリからGoogleスプレッドシートを自動生成する機能はありません。
