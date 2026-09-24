# CrowdStrike公開のnpmパッケージがShai-Hulud系サプライチェーン攻撃で侵害

- **日付**: 2026-09-19
- **出典**: [Socket](https://socket.dev/blog/ongoing-supply-chain-attack-targets-crowdstrike-npm-packages), [CyberSecurityNews](https://cybersecuritynews.com/npm-supply-chain-attack-crowdstrike/)
- **分類**: 関連

## 概要

セキュリティ企業CrowdStrikeが公開しているnpmパッケージ群が、継続中のサプライチェーン攻撃「Shai-Hulud」系統の悪意あるコードに侵害されていたことが判明した。過去に人気パッケージ「tinycolor」を狙った攻撃と同一のマルウェアが使用されており、CI/CDパイプラインや開発者端末からのシークレット窃取が懸念される。

## 詳細

Socketなどの報告によれば、CrowdStrikeが公開する複数のnpmパッケージが侵害を受け、悪意あるbundle.jsファイルが混入していたことが確認された。このbundle.jsのSHA-256ハッシュ値は「46faab8ab153fae6e80e7cca38eab363075bb524edd79e42269217a083628f09」と識別されている。

攻撃手法は、これまでのShai-Hulud（およびその派生・小型版であるMini Shai-Hulud／ChainDrop系統）の攻撃と同様に、正規の認証情報スキャナーであるTruffleHogを悪用して開発者やCI/CDのトークン、クラウドサービスの認証情報、環境変数を収集し、ハードコードされたWebhookやGitHub Actionsワークフロー経由で外部に持ち出す手口とみられる。窃取した認証情報を用いて他の正規パッケージへの感染を広げる自己増殖的な性質を持つ点も従来の系統と共通している。

セキュリティ企業各社は、影響を受けた可能性のある組織に対し、CI/CDパイプラインおよび開発者端末の総点検と、露出した可能性のあるnpmトークンやその他のシークレットの即時ローテーションを推奨している。npmエコシステムを狙ったShai-Hulud系ワームは2026年に入り複数回にわたり拡大を続けており、AIコーディングアシスタントのセッション乗っ取りを起点とした感染事例（2026年9月16日報告）なども含め、サプライチェーン全体でのソフトウェア部品構成の管理強化が引き続き課題となっている。

---

## 関連記事

- [AIコーディングアシスタントのセッション乗っ取りからShai-Hulud系ワームが社内リポジトリ約100件に拡散（Mandiant報告）](../articles/2026-09-16-shai-hulud-ai-coding-assistant-hijack.md) - 同じShai-Hulud系統のワームによる別のサプライチェーン侵害事例
