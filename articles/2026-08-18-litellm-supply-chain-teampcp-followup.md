# TeamPCPサプライチェーン攻撃の全容判明 ― LiteLLM経由で2,500社超・43.4万件のCI/CDパイプラインに影響

- **日付**: 2026-08-18
- **出典**: [Security Affairs](https://securityaffairs.com/197377/hacking/litellm-supply-chain-attack-technology-banking-and-healthcare-the-most-affected.html)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 続報

## 概要

2026年2月末〜4月にTeamPCPが実施した多段階サプライチェーン攻撃について、被害範囲の全容を示す新たな分析が公開された。侵害されたAIゲートウェイLiteLLMの悪意あるパッケージ（v1.82.7／v1.82.8）を通じて、2,500社超・CI/CDパイプライン43.4万件超に影響が及んでいたことが判明。AWS、NVIDIA、Cisco、Salesforceなど技術大手のほか、金融・医療分野の大手企業も被害を受けていた。

## 詳細

### これまでの経緯（既報）

TeamPCPは、コンテナセキュリティスキャンツールTrivyのGitHubサービスアカウントに対する不完全なクレデンシャルローテーションを突破口に、Trivy Actionを侵害。そこで取得した認証情報を踏み台に、Checkmarx、Bitwarden CLI、AIゲートウェイLiteLLM、Telnyx Python SDK、KICSを連鎖的に侵害した。LiteLLMについては、2026年3月頃にPyPI上のパッケージバージョン1.82.7および1.82.8が悪意あるコードに置き換えられ公開されていたことが確認されている。

### 新たに判明した被害範囲

今回の分析（通称「SANDCLOCK」LiteLLMサプライチェーン攻撃）によると、侵害されたLiteLLMパッケージを利用していた2,038件のリポジトリで認証情報が露出し、技術・金融・医療・小売など多岐にわたる業種に影響が及んでいたことが判明した。影響を受けた組織は2,500社超、CI/CD環境は43.4万件超にのぼり、2026年におけるAIサプライチェーン侵害としては最大規模とされる。

### 侵害の技術的連鎖

LiteLLMのCI/CDパイプラインが、侵害済みのTrivyを自動的にインストールする構成になっていたことが、被害拡大の直接的な原因となった。これにより、クラウドインフラのアクセスキー、リポジトリアクセストークン、SSH認証情報、Kubernetesシークレット、AIプロバイダーのAPIキーなど、機密性の高い認証情報一式が広範に露出した。

### 影響を受けた業種・組織例

- 技術／SaaS：AWS、NVIDIA、Cisco、Salesforce、Zscaler、NGINX、Roku、BT Groupなど
- 金融：S&P Global、London Stock Exchange Group、Thomson Reutersなど
- ヘルスケア／製薬：Roche、Philips、Regeneronなど

### 推奨対応

研究者は、LiteLLM関連の環境に紐づく機微データはすべて侵害された前提で対応するよう強く推奨している。具体的には、関連するクラウドAPIキー・リポジトリトークン・SSH鍵・Kubernetesシークレット・AIプロバイダーAPIキーの積極的な失効（aggressive credential revocation）と再発行、CI/CDパイプラインにおける依存関係の出所検証強化が求められる。

