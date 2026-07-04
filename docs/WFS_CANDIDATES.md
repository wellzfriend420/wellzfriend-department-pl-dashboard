# WFS Candidates

本書は正式標準ではなく、部門別PLで検証する候補一覧です。

## Status

**Current Status: Candidate**

このシステムはWellzFriend Standard策定のベースモデルです。運用しながら改善し、正式版WFSへ反映します。

| 候補 | 仮説 | 昇格条件 |
|---|---|---|
| DATA/CALC/REPORT/DASHBOARD分離 | 保守とWeb移行が容易 | 3回以上の改修で責務が崩れない |
| README_AI必須化 | AIの引継ぎ時間を短縮 | 別AIによる改修テストに成功 |
| SETTINGSへの会社差異集約 | テンプレート化しやすい | 別会社データでコード変更不要 |
| 合成データテスト | 秘密情報なしで品質確認可能 | 主要計算と境界値を再現可能 |

昇格時は根拠、適用範囲、例外、責任者、決定日をWellzFriend_OSへ記録します。
