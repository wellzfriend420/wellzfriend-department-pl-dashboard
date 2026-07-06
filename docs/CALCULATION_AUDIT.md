# Calculation Audit

## 正式な集計経路

```text
DATA → CALC → REPORT / DASHBOARD / EXECUTIVE_REPORT
```

CALCを唯一の計算層とする。REPORT、DASHBOARD、EXECUTIVE_REPORTは表示層であり、同じ金額を別々に集計しない。

## シート責務

| シート | 責務 | 許可する式 |
|---|---|---|
| DATA | 元明細、年月正規化、PL区分付与 | 行単位の自動列 |
| CALC | 月次、累計、前年同期、部門比較、製造経費科目内訳 | SUMIFS、比率、差額 |
| REPORT | 部門別累計PLの表示 | CALCへのXLOOKUP、表示整形 |
| DASHBOARD | 経営判断表示、グラフ参照 | REPORTまたはCALCへの直接参照、表示整形 |
| EXECUTIVE_REPORT | A4横1枚の提出用経営サマリー | CALCへのXLOOKUP、表示整形 |

## 外注加工費の照合

1. DATAで会計年度開始月から表示月までを対象にする。
2. 年月、部門、勘定科目 `[製]外注加工費` を照合する。
3. CALCの月次外注加工費と累計外注加工費を照合する。
4. REPORTの製造経費内訳がCALCの累計列を参照していることを確認する。
5. DATA、CALC、REPORTの3金額が一致していることを合格条件とする。

顧客の実金額はGitHubへ記録しない。

## 差異が出た場合の確認順

1. DATAにサンプル明細と実運用明細が混在していないか。
2. 同じファイルを複数回取り込んでいないか。
3. DATAの年月が月初日へ正規化されているか。
4. 部門名と勘定科目名がSETTINGSと完全一致しているか。
5. 会計年度開始月と表示月が正しいか。
6. CALCの部門行と合計行が一致するか。
7. REPORTにSUMIFSまたはDATA直接参照が残っていないか。
8. DASHBOARDに集計式が残っていないか。
9. EXECUTIVE_REPORTにSUMIFSまたはDATA直接参照が残っていないか。

## 禁止事項

- REPORTからDATAを直接参照する。
- DASHBOARDでSUMIFSやXLOOKUPを使って再集計する。
- EXECUTIVE_REPORTでDATAを直接参照する、またはSUMIFSで再集計する。
- サンプル値を実運用DATAへ残す。
- 差異の理由を確認せず手入力でREPORTを合わせる。
