# Open VSXで「Evil Twin」型の悪性拡張機能77件を検出・削除、ChainDropキャンペーンの一部と判明

- **日付**: 2026-08-05
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/open-vsx-removes-77-malicious-evil-twin.html)
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/77-open-vsx-extensions-found-harvesting-developer-info/)
- **トピック**: [ChainDrop npmサプライチェーンワーム（2026年8月）](../topics/chaindrop-npm-supply-chain-worm-2026.md)
- **分類**: 続報

## 概要

VS Code拡張機能マーケットプレイス「Open VSX」において、正規の拡張機能になりすました「Evil Twin（そっくりさん）」型の悪性拡張機能77件が確認され、削除された。これらはnpmを標的とした自己増殖型ワーム「ChainDrop」と同一キャンペーンの一部と特定されている。開発環境やGit・CIのメタデータを外部へ送信する機能を持っていた。

## 詳細

セキュリティ企業Manifold Securityの分析によると、これら「Evil Twin」拡張機能は2026年7月26日から8月1日にかけてOpen VSXへアップロードされた。正規拡張機能の名前・namespace・説明文をそのまま流用しつつ、無関係のアカウントから低いバージョン番号（例：0.0.1）で公開されており、同梱の`extension.js`の中身を差し替え、データ収集機能を「匿名の利用状況メトリクス」と偽って組み込んでいた。パッケージが説明文で謳っていた本来の機能は一切提供されていなかった。

77件のうち58件は比較的小規模なシステム情報のみを送信していたが、残る19件はより広範な偵察機能を持ち、開発者情報・Gitリポジトリ・CI（継続的インテグレーション）のメタデータまで外部へ送信していた。これにより、プライベートリポジトリの名称やパスといった情報が漏えいするおそれがあった。

該当パッケージは2026年8月3日時点でOpen VSXから削除済み。MicrosoftはこのOpen VSXでの活動を、同日発覚したnpmのkeyv・cacheableを狙った自己増殖ワームと同一の「ChainDrop」キャンペーンの一部と位置付けている。

### 影響範囲

- 対象：Open VSXマーケットプレイス上の拡張機能77件
- アップロード期間：2026年7月26日〜8月1日
- 削除日：2026年8月3日
- 窃取対象：システム情報（58件）、開発者・Git・CIメタデータ（19件）

### セキュリティ上の考察

拡張機能マーケットプレイスにおける「なりすまし」型の攻撃は、開発者が名前や説明文だけで信頼性を判断しがちな点を突く手口であり、ダウンロード数・公開日・発行者アカウントの実績確認など、サプライチェーン全体でのゼロトラスト的な検証が必要となる。

---

## 関連記事

- [「ChainDrop」自己増殖型npmワーム、keyv・cacheable等450パッケージ・2,200超のバージョンに感染](../articles/2026-08-04-chaindrop-npm-worm.md) - 同一のChainDropキャンペーンによるnpm側の攻撃
