---
name: Feature
about: 機能追加
title: "feature: "
labels: ["feature"]
assignees: []
---

<!--
======================== ガイド（作成後も残してOK） ========================

■ タイトルの付け方（例）
  - feat: 匿名コメントの作成APIを追加
  - chore: Render で Web サービス作成（Auto Deploy OFF）
  - docs: README に ER 図へのリンクを追加
  - fix: コメント一覧APIでN+1解消
  - refactor: CommentsController のサービス分離
  - perf: コメント取得のキャッシュを追加
  - test: Comments API のリクエストスペック追加
  - ci: GitHub Actions でRubocopを実行
  - build: Dockerfile を production 用に調整

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
