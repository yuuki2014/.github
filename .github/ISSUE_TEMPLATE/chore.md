---
name: Chore
about: 設定変更・運用整備・リポジトリ衛生など（挙動を変えない作業）
title: "chore: "
labels: ["chore"]
assignees: []
---

<!--
======================== ガイド（作成後も残してOK / 画面では非表示） ========================

■ これは何用？
- アプリの“仕様やユーザー価値”は変えず、開発や運用を整える作業に使うテンプレです。
  例：.gitignore整備、Dependabot/CodeQLの有効化、Renderの設定、README追記、エディタ設定、Linter導入 等

■ タイトル例（先頭に 'chore: '）
- chore: リポジトリ衛生（.gitignore整備・不要追跡の解除）
- chore: Dependabot と CodeQL を有効化
- chore: Render Webサービス作成（Auto Deploy OFF）
- chore: README に起動手順とライセンスを追記
- chore: RAILS_MASTER_KEY をRenderに登録しcredentials方針を確立

■ ブランチ名（kebab-case）
- chore/repo-hygiene
- chore/enable-dependabot-codeql
- chore/render-web-service
- chore/readme-setup-section
- chore/credentials-policy

■ コミット例（Conventional Commits 推奨）
- chore(repo): add rails+node .gitignore and remove tracked junk
- chore(security): enable Dependabot security updates
- chore(ci): set up CodeQL for Ruby
- chore(infra): create Render web service and disable auto deploy
- chore(docs): update README with setup and license links

■ “choreとfeatの線引き”
- ユーザーから見える挙動が増える/変わる → feat
- 仕様は同じで内部構造だけ整理        → refactor
- 速度だけ上がる（仕様は同じ）        → perf
- バグ修正                               → fix
- 文書だけ                               → docs
- CI定義                                  → ci
- ビルド/依存/パッケージ                 → build
- インフラ（Render/DB/監視）             → infra（※迷ったらchoreでも可）

■ 受け入れ基準のコツ
- “何を見れば完了と判断できるか”を **URL / コマンド結果 / スクショ / 設定の差分** で書く
- レビュワー（未来の自分）がクリック/実行して即座に確認できる表現にする
===============================================================================================
-->

# なぜ必要か（背景・目的）
- 例）誤コミット防止のため、.gitignore とリポジトリ衛生を整える
- 例）脆弱性通知と静的解析を自動化して保守性を高める
- 例）誤push即デプロイを避けるため Render の Auto Deploy をOFFにする

## スコープ（このIssueでやること）
- [ ] 作業A
- [ ] 作業B

## 受け入れ基準（完了条件 / Definition of Done）
- [ ] （例）`git status` がクリーンで `node_modules/`, `log/`, `tmp/` が追跡されていないスクショを添付
- [ ] （例）GitHub の **Security & analysis** で Dependabot / CodeQL が Enabled になっているスクショ
- [ ] （例）Render ダッシュボードで Web Service が作成され、**Auto Deploy: OFF** のスクショ
- [ ] （例）README に起動/デプロイ手順の該当節が追記されている差分リンク

## 詳細（作業手順・コマンド・触るファイル）
- 対象ファイル/ディレクトリ：  
  - 例）`.gitignore`, `README.md`, `.github/` 配下, Render 設定
- コマンド例（必要なら貼る）：  
  - 例）`git rm -r --cached node_modules tmp log`  
  - 例）`echo 'RAILS_MASTER_KEY=xxxx'`（実値は載せない）
- 注意：秘密情報（APIキー・`config/master.key`）は**絶対にコミットしない**

## スコープ外（このIssueではやらない）
- 例）APIの新規実装、UI変更、DBスキーマ変更（別Issueへ）

## 影響範囲・依存関係
- 依存するIssue/PR：  
- 影響する機能/設定：  

## スクショ / ログ / 参考リンク
- スクショや設定画面のURL
- リンク：README該当箇所、Render ダッシュボード、GitHub設定画面 など

<!--
============================== よくあるchoreの“雛形” ==============================

【雛形1】.gitignore整備＆不要追跡解除
- ブランチ: chore/repo-hygiene
- やること:
  - rails+node向け .gitignore を追加
  - 既に追跡中の不要物をキャッシュから外す（例：log/*, tmp/*, node_modules/）
  - 秘密物が履歴にないか確認（config/master.key, .env*）
- コミット例:
  - chore(repo): add rails+node .gitignore
  - chore(repo): untrack log/, tmp/, node_modules/ and cleanup
- 受け入れ基準:
  - `git status` がクリーン
  - PR差分に秘密ファイルが含まれていない

【雛形2】Dependabot / CodeQL 有効化
- ブランチ: chore/enable-dependabot-codeql
- やること:
  - Settings > Security & analysis で Dependabot security updates を Enable
  - Code scanning > CodeQL を Ruby で Set up
- コミット例:
  - chore(security): enable Dependabot security updates
  - chore(ci): set up CodeQL (ruby)
- 受け入れ基準:
  - Security タブで両方 Enabled のスクショ

【雛形3】Render Webサービス作成（Auto Deploy OFF）
- ブランチ: chore/render-web-service
- やること:
  - GitHub Private リポを Render に接続
  - Auto Deploy を OFF
  - Health Check Path は後で `/up` を設定予定（メモ）
- コミット例:
  - chore(infra): create Render web service and disable auto deploy
- 受け入れ基準:
  - Render ダッシュボードのスクショ（サービスが作成され、Auto Deploy OFF）

【雛形4】RAILS_MASTER_KEY 方針と登録
- ブランチ: chore/credentials-policy
- やること:
  - `bin/rails credentials:edit` で master.key 作成（コミットしない）
  - Render > Environment に `RAILS_MASTER_KEY` を登録
  - README の Config 節に“秘密は環境変数で管理”を追記
- コミット例:
  - chore(docs): add credentials policy to README
- 受け入れ基準:
  - Render 環境変数のスクショ（値は黒塗り）と README の差分

【雛形5】README の最小整備
- ブランチ: chore/readme-setup
- やること:
  - 概要/技術スタック/起動手順/デプロイ方針/ライセンス/注意書き を追記
- コミット例:
  - chore(docs): update README with setup & deploy sections
- 受け入れ基準:
  - READMEの該当章が存在し、手順で実際に起動できる
===================================================================================
-->
