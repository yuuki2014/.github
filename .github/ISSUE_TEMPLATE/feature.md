---
name: "💡 機能追加（Feature）"
about: "ユーザーに価値が見える変更全般（API/UI/DB 追加など）"
title: "💡 feat: "
labels: ["feature"]
assignees: []
---

<!--
======================== ガイド（作成後も残してOK） ========================

■ タイトルの付け方（例）
  - 💡 feat: 新機能/匿名コメントの作成APIを追加
  - 🧹 chore: 雑務/Render で Web サービス作成（Auto Deploy OFF）
  - 📝 docs: ドキュメント/README に ER 図へのリンクを追加
  - 🐛 bug: バグ修正/コメントの表示がおかしい
  - ♻️ refactor: 挙動を変えない中身の整理/CommentsController のサービス分離
  - ⚡ perf: パフォーマンス改善/コメント取得のキャッシュを追加、コメント一覧APIでN+1解消
  - 🧪 test: テスト/Comments API のリクエストスペック追加
  - 🛠️ ci: CI関連(ワークフロー修正等)/GitHub Actions でRubocopを実行
  - 📦 build: ビルド設定/Dockerfile / docker-compose を整える、Rails をローカルで立ち上げる
  - 🏗️ infra: Render へデプロイ、DB/ストレージ等の外部サービス設定
  - 🚀 epic: MVPリリース/大目標/まとまり

■ ブランチ名の付け方（kebab-case）
  - feat/comments-create-endpoint
  - chore/render-web-service
  - docs/readme-erd-link
  - fix/comments-n-plus-one
  - refactor/comments-service-object
  - perf/comments-cache
  - test/comments-request-spec
  - ci/rubocop-workflow
  - build/dockerfile-prod

■ コミットメッセージ規約（Conventional Commits 推奨）
  形式:  <type>(<scope>): <summary>
  例   : feat(comments): create endpoint for anonymous post
         fix(db): add missing index for comments.book_id
         chore(ci): enable CodeQL scanning
  補足 : 本文は空行を1つ入れて詳細。フッターに Close #123 等を記載。

■ PR タイトルの付け方（Issueに対応させる）
  - [feat] 匿名コメントの作成APIを追加（Close #12）
  - [chore] Render: Web サービス作成（Auto Deploy OFF）
  - [docs] README: ER 図リンクを追加

■ 受け入れ基準（例の作り方）
  - どのURL/コマンド/ログで「できた」と判定するかを書いておく
  - スクショや cURL の返り値、Rails ログ抜粋など“客観的”な根拠を用意

■ ラベルの目安
  - feature / fix / chore / docs / perf / test / ci / build / security / infra など
ユーザーに見える振る舞いが増えた？ → feat
バグ修正？ → fix
速度/負荷のみ改善？ → perf
仕様は同じで内部整理？ → refactor
テストだけ？ → test
文書だけ？ → docs
CI定義？ → ci
ビルド/依存/パッケージ？ → build
セキュリティ目的が主？ → security
インフラ（Render/DB/監視）？ → infra
上記どれでもない雑務・運用設定 → chore

⭐️ラベル設計（type / area / priority）
type: epic / feature / bug / refactor / perf / docs / test / chore / ci / build
area: api / extension / frontend / backend / db / infra（必要に応じて追加）
priority: P0 / P1 / P2（P0=今すぐ、P1=今週、P2=来週以降）
迷ったら：
親イシュー → type: epic だけ付ける
子イシュー → type:* ＋ area:* ＋ priority:*

⭐️Projects（Tableビュー）の列
Title（自動）
Status：Todo / In progress / In review / Done
Priority：P0 / P1 / P2
Assignee
Milestone（例：MVP v0.1）
（余裕が出たら）Size：S / M / L
4) エピック（親）と子のつなぎ方
親（epic: 🚀）の本文にチェックリストで子を列挙
子イシューの本文の先頭に Parent: #<親番号> を1行入れる
PR本文には Closes #<子番号> を入れて自動クローズ
=======================================================================
-->

# なぜ必要か（背景・目的）
- 何のためのIssueか：ユーザー価値 / リスク回避 / デプロイ準備/運用改善 など

## スコープ（このIssueでやること）
- [ ] 作業1
- [ ] 作業2

## 受け入れ基準（完了条件 / Definition of Done）
- [ ] 動作・画面・設定が**確認できる客観的な条件**（URL、コマンド結果、ログ、スクショ 等）
- [ ] READMEや設定の**反映箇所**が更新されている
- 例:
  - [ ] `POST /api/v1/comments` に cURL で投げると 201 が返り、JSON に作成結果が含まれる
  - [ ] README の「デプロイ手順」に Render の操作が追記されている

## 詳細（コードレベルの観点）
- 触るファイル/ディレクトリ：
- 主要メソッド/設定項目：
- テスト観点（最低限の確認手順でも可）：

## スコープ外（このIssueではやらない）
- 明確に除外すること（次Issueへ切る内容）

## 影響範囲・依存関係
- 依存するIssue/PR：
- 影響する機能/設定：

## スクショ / ログ / 参考リンク
- 画像やコンソール出力
- 関連ドキュメント・仕様リンク

<!--
注意（テンプレの運用メモ：作成後にこのコメントは残してOK）
- タイトルは短く具体的に（例：chore: enable Dependabot）
- 関係者を @メンション（将来の自分含む）
- 作業時間の目安があれば軽く書く
-->
