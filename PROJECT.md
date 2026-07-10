# PROJECT.md（作業開始の入口）

## このファイルの役割
- このファイルは、このプロジェクトで最初に読む入口である。
- ここでは案件固有の目的、完成形、注意点、現在の状態だけを簡潔に保持する。
- `D:\program\workspace-meta` の共通文書は必要時だけ参照する。

## 最初に読む順序
1. この `PROJECT.md`
2. `README.md`
3. 必要な対象ファイル
4. プロジェクト固有ルールが必要な場合だけ `RULES.md`
5. 長期継続、未完了、環境・設定・運用変更、引き継ぎがある場合だけ `state_compact.json`
6. 横断影響がある場合だけ [GLOBAL_ACTIVE.md](/D:/program/workspace-meta/GLOBAL_ACTIVE.md)

## 必要時だけ読むもの
- workspace-meta 自体の管理、長期再開、引き継ぎ、横断確認:
  [SESSION_CORE.md](/D:/program/workspace-meta/SESSION_CORE.md)
- 長い共通運用の詳細:
  [AGENTS_DETAIL.md](/D:/program/workspace-meta/AGENTS_DETAIL.md)
- 横断変更の履歴:
  [GLOBAL_CHANGES.md](/D:/program/workspace-meta/GLOBAL_CHANGES.md)
- docs 詳細ルールやフェーズ別詳細:
  `RULES_DETAIL.md`
- 調査成果物:
  `docs/RESEARCH.yaml`
- 設計成果物:
  `docs/DESIGN.md`
- 実装成果物:
  `docs/PATCH.yaml`
- 検証成果物:
  `docs/VERIFY.md`

## このプロジェクトの概要
- 目的：FFXI エミュレートサーバーの構築、ソースコード (C++) の修正、およびデータベース (SQL) の管理。
- 成果物（期待する完成形）：安定稼働するプライベートサーバー環境および、カスタマイズされたゲームコンテンツ。
- 主な技術要素（言語 / ライブラリ / ツール）：C++, Lua, SQL (MariaDB), Docker, CMake, ZeroMQ。

---

## 現在の作業フェーズ

> **フェーズは固定して運用する。フェーズを跨ぐ作業は行わない。**

- [ ] 🔍 調査フェーズ　→ 目的：情報収集と現状把握のみ
- [ ] 🔨 実装フェーズ　→ 目的：コードの作成・変更のみ
- [ ] 🔧 修正フェーズ　→ 目的：バグ修正・設定修正のみ
- [ ] 🧪 検証フェーズ　→ 目的：テスト・動作確認のみ
- [ ] 🚀 運用フェーズ　→ 目的：本番稼働・監視のみ

## この案件で絶対に外せないこと
- 秘密情報の実値を `PROJECT.md` や `docs/*.md` に書かない。
- 本番反映、削除、上書き、認証情報利用、外部公開設定変更は必ずユーザー承認を得る。
- 短時間・単発作業では `state_compact.json` の読込・更新を必須にしない。
- `state_compact.json` を現在状態の主軸とする。

## この案件特有の注意
- （例）本番環境に影響する操作は事前確認必須
- （例）削除・上書き禁止のディレクトリがある

---

## 入口チェック
- [ ] 必要なら `RULES.md` を読んだ
- [ ] 横断影響の有無を判定した
- [ ] 長期継続、未完了、環境・設定・運用変更、引き継ぎがある場合だけ `state_compact.json` を読んだ
- [ ] Claude レビュー必須条件に該当する場合だけレビューを実施した

## 完了前チェック
- [ ] 更新条件に該当する場合だけ `state_compact.json` を更新した
- [ ] 必要なら `work_journal.md` を更新した
