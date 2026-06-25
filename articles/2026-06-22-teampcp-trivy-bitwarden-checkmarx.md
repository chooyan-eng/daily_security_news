# TeamPCPによるサプライチェーン攻撃：Trivy・Bitwarden CLI・Checkmarxを2ヶ月間侵害

- **日付**: 2026-06-22
- **出典**: [The Hacker News](https://thehackernews.com/2026/04/bitwarden-cli-compromised-in-ongoing.html)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 新規

## 概要

「TeamPCP」と呼ばれる脅威アクターが2026年2月末から約2ヶ月間にわたり、セキュリティスキャンツール Trivy、パスワードマネージャー Bitwarden CLI、セキュリティ分析ツール Checkmarx を連鎖的に侵害するサプライチェーン攻撃を実施した。開発者・CI/CDパイプラインの認証情報・クラウドシークレット・SSHキーが標的で、Checkmarxの96GBの非公開GitHubデータがLAPSUS$の恐喝ポータルに公開される事態となった。

## 詳細

### 攻撃の連鎖（タイムライン）

#### フェーズ1: Trivy侵害（2026年2月末〜3月）

攻撃はAqua Securityの `aqua-bot` サービスアカウントへの不完全なクレデンシャルローテーションを悪用することから始まった。

- 2026年3月19日：攻撃者が `aquasecurity/trivy-action`（76/77バージョンタグ）および `aquasecurity/setup-trivy`（全タグ）に悪意あるコードをフォースプッシュ
- 影響：これらのバージョンをpinしていたCI/CDワークフローがすべてマルウェアを実行し、クラウド認証情報・SSHキー・GitHubトークン・npm publish権限・Kubernetes設定ファイルを収集・流出

#### フェーズ2: Checkmarx侵害（2026年3月〜4月）

- 2026年3月23日：攻撃者がTrivy侵害を踏み台としてCheckmarxのGitHubリポジトリへの不正アクセスを実施
- 2026年4月28日：Checkmarxの非公開GitHubデータ96GBがLAPSUS$の恐喝ポータルに掲載されたことを確認

#### フェーズ3: Bitwarden CLI侵害（2026年4月）

- 攻撃者が `@bitwarden/cli@2026.4.0` として悪意あるパッケージをnpmに公開
- **悪意あるpayload**: インストール時に `preinstall` フックが実行され、Bunランタイムをダウンロードし、難読化された約10MBのJavaScriptペイロードを起動
- **窃取対象**: GitHubトークン・npmトークン・SSH鍵・.envファイル・シェル履歴・GitHub Actionsシークレット・クラウドシークレット
- **流出先**: 攻撃者管理のプライベートドメインおよびGitHubコミットとして

### LiteLLM・Telnyx SDK等への波及

TeamPCPはTrivyで取得した認証情報を使ってさらに多くのツールへの横展開を実施：

- **LiteLLM**: AIゲートウェイライブラリへの侵害（既存トピック `litellm-ai-gateway-vulnerabilities` と関連）
- **Telnyx Python SDK**: 通信API SDKへの侵害
- **KICS (Checkov Infrastructure as Code scanner)**: IaCセキュリティスキャナーへの侵害

### 最終的な被害

- 攻撃者がCI/CDパイプラインで収集した認証情報を使用し、OpenAI・Vercel等の大手企業への二次侵害が確認された
- 約2ヶ月にわたる侵害が発覚まで継続していたことから、サプライチェーン検知の困難さが改めて示された

### 技術的分析

攻撃者の手口は以下の特徴を持つ：
- **認証情報の収集と即時悪用**: 開発環境・CI/CDシークレット・クラウド認証情報の連鎖的な窃取
- **難読化**: 10MB超の高度に難読化されたJSペイロードにより静的検出を回避
- **信頼チェーンの悪用**: セキュリティツール自体を感染させることで、ユーザーの信頼を悪用

### 対策と教訓

1. GitHubアクションのバージョンはコミットSHAでpinし、タグではなくimmutableな参照を使用する
2. npm install 前に `--ignore-scripts` フラグでpreinstallフックの実行を防ぐ
3. CI/CD環境のシークレットスコープを最小権限に絞り込む
4. ビルドパイプラインの異常なネットワーク通信を監視する

---

## 関連記事

- [Mastra npm サプライチェーン攻撃（2026年6月）](../articles/2026-06-17-mastra-npm-supply-chain.md) - npmエコシステムを狙う同期間のサプライチェーン攻撃の類似事案
