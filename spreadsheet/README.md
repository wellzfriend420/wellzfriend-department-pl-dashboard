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
- DASHBOARD / REPORT: CALC onlyを参照する

## Rebuild policy

現MVPはGoogle Sheetsが利用実体です。自動再構築コードは、実運用で入力形式と科目分類が安定した後に追加します。それまでは本仕様とREADME_AIを正本として変更差分を管理します。
