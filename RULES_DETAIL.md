# RULES_DETAIL.md（プロジェクト固有ルール / Detail）

## docs 契約
- `docs/RESEARCH.yaml`:
  `purpose / facts / unresolved / design_handoff`
- `docs/DESIGN.md`:
  `管理情報 / 目的 / 要求事項 / 制約 / 実装対象 / 非対象 / 変更対象ファイル / 実装手順 / テスト観点 / リスク / codexへの実装指示`
- `docs/PATCH.yaml`:
  `design_id / result / reason / summary / changed_files / verify_request`
- `docs/VERIFY.md`:
  `管理情報 / 検証対象 / 検証結果 / PASS / FAIL 判定 / 発見した問題 / 原因推定 / 戻し先 / 修正提案 / 再検証条件`

## 設計フロー契約
- 設計記録が必要な案件では、`docs/DESIGN.md` の管理情報に少なくとも以下を埋めること。
- `作成者`
- `ステータス`
- `実装開始条件`
- AI レビュー必須条件に該当する場合は、次も埋める。
  - `AIレビュー実施`（レビュー担当 AI 名を含む）
  - `AIレビュー結果`
  - `AIレビュー反映状況`
- `ステータス` は少なくとも `draft / reviewed / approved / superseded` を使い分ける。
- `reviewed` は実装担当以外の AI によるレビュー完了済み、`approved` は Human または案件ルール上の承認完了を意味する。
- `AIレビュー結果` には `pass / issues_found / blocked` のいずれかを記載する。
- `AIレビュー反映状況` には `未反映 / 一部反映 / 反映済み` のいずれかを記載する。

## 実装着手条件
- `RULES.md` の AI レビュー必須条件に該当する場合だけ、レビュー完了を実装開始条件とする。
- レビューで `issues_found` となった場合、未反映の重大指摘を残したまま該当変更を実行しない。
- 軽微で可逆な作業には `docs/DESIGN.md`、AI レビュー、`state_compact.json` 更新を強制しない。
- Human 承認が必要な操作は、レビュー有無にかかわらず承認まで実行しない。

## FAIL 分類
| 分類 | 典型例 | 戻し先 |
| --- | --- | --- |
| design | 調査不足、設計矛盾、静的検証失敗 | 実装担当以外の AI |
| implementation | 実装ミス、仕様未反映 | Codex |
| environment | 権限不足、外部サービス、環境検証失敗 | Codex または Human |
| device | 実機依存、導入先依存 | Codex または Human |
| approval | 承認待ち、判断待ち | Human |

## 再実行ルール
- `design` は調査または設計補強完了まで次フェーズへ進めない。
- AI レビュー必須条件に該当する `design` は、レビュー完了まで次フェーズへ進めない。
- `environment` は原因切り分けが終わるまで本番判断へ進めない。
- `approval` は明示承認があるまで停止する。
