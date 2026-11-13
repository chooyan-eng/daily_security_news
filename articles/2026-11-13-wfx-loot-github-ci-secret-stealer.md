# 「wfx-loot」キャンペーン、窃取したGitHubトークンで6万超のリポジトリにCIシークレット窃取コードを注入

- **日付**: 2026-11-13
- **出典**: [Aikido Security](https://www.aikido.dev/blog/compromised-github-accounts-push-ci-secret-stealer-to-tens-of-thousands-of-repositories)
- **トピック**: [wfx-loot GitHub CIシークレット窃取キャンペーン（2026年11月）](../topics/wfx-loot-github-ci-secret-stealer-2026.md)
- **分類**: 新規

## 概要

11月10日以降、窃取されたGitHubトークンを用いてリポジトリにCIシークレット窃取コードを注入する「wfx-loot」キャンペーンが報告された。4,837の侵害アカウントが61,764リポジトリにプローブPRを作成し、1,800超のリポジトリで実際にペイロードが実行された。GitHub自体の脆弱性ではない。

## 詳細

### 攻撃の流れ（Aikidoなどの分析による）

1. **プローブ**: 窃取したトークンで、ブランチ `wfx-docs` から「docs: dependency audit notes」という無害に見えるPRを作成し、書き込み権限の有無を確認する。このPRが存在する時点で、作成元アカウントは侵害されている。
2. **注入**: CIメンテナンスを装ったコミットでスティーラーを追加する。注入先は既存ワークフロー、新規ワークフローファイル、既存シェルスクリプト、npmの `postinstall` フックのいずれか。コミットタイトルの例: 「ci: refresh build cache」「chore: add ci helper」「chore: add dependency audit workflow」（「ci: restore」「ci: cleanup」の報告もある）。
3. **実行と痕跡消去**: 次のワークフロー実行または `npm install` でペイロードが動作。攻撃者は1分以内に変更をrevertし、ワークフロー実行とログを削除する。そのため痕跡がないことは安全の証明にならない。

### 窃取対象と永続化

- GitHub Actionsのsecrets/variables、ワークフローの `GITHUB_TOKEN`、OIDCトークン、Actionsランタイムトークン。
- AWS・Azure・GCPのクラウドセッション取得を試行。
- 永続化: AWSアクセスキーの新規作成、IAMロール信頼ポリシーの書き換え、Entra IDへの `wfx-ci-*` という名前のフェデレーション資格情報の追加。

### 規模

- 侵害アカウント: 4,837
- プローブPRが作成されたリポジトリ: 61,764（Chainguardは6万超と表現）
- ペイロードが実行されたリポジトリ: 1,806〜1,835（情報源により差がある）
- npm、Go、Packagist、PyPI、crates.ioにパッケージを公開しているアカウントが少なくとも50含まれ、公開トークン窃取による悪性パッケージ公開への波及が懸念される。
- 10月の「GhostAction」キャンペーンの被害アカウントが有意に多く含まれるが、Aikidoは別アクターと評価している。

### 確認・対処

- リポジトリで `wfx-docs` ブランチ、上記タイトルのPR、上記コミットメッセージ（11月10日以降）を検索する。
- ペイロードが実行された場合、そのワークフローから到達可能な全シークレットとクラウドロールを侵害済みとして扱いローテーションする。
- AWSのロール信頼ポリシー、不審なアクセスキー、Entra IDの `wfx-ci-*` フェデレーション資格情報を点検する。
- 予防: PATの細粒度化・短期限化、ブランチ保護とワークフロー変更のレビュー必須化、OIDCの `sub` クレーム条件の厳格化、`npm ci --ignore-scripts` の検討。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

