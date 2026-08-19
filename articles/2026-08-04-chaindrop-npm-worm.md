# 「ChainDrop」自己増殖型npmワーム、keyv・cacheable等450パッケージ・2,200超のバージョンに感染

- **日付**: 2026-08-04
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/open-vsx-removes-77-malicious-evil-twin.html)
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/08/04/chaindrop-supply-chain-compromise-anatomy-self-propagating-worm/)
- **トピック**: [npm keyv/cacheable サプライチェーンワーム（2026年8月）](../topics/npm-keyv-cacheable-worm-2026.md)
- **分類**: 続報
## 概要

npmの人気パッケージ「keyv」「cacheable」およびその依存パッケージ群に対し、自己増殖型のクレデンシャル窃取ワーム「ChainDrop」による攻撃が発生した。攻撃はメンテナーのGitHubアカウント侵害を起点に、450以上のユニークなパッケージ・2,244件のアーティファクトへ拡散し、週間数千万ダウンロード規模のエコシステムに影響を与えた。

## 詳細

2026年8月4日UTC10:53頃から、攻撃者はkeyv・cacheableおよびその共通依存パッケージの正規npmパッケージに対し悪意あるバージョンを公開し始めた。この自己増殖ワームは「keyv-shai-hulud」とも呼ばれ、過去に猛威を振るった「Shai-Hulud」ワームの亜種（Mini Shai-Hulud）を用いているとみられるが、直接の帰属は現時点で確認されていない。

悪意あるリリースには、Bunベースの大規模かつ難読化されたJavaScriptペイロードが仕込まれたnpm preinstallフックが追加されており、パッケージのインストール完了前に自動実行される。実行されると、開発者のワークステーションやCI/CD環境からnpm・GitHub・クラウド・インフラ関連の認証情報を探索して窃取する。さらに窃取した認証情報を悪用し、他のメンテナーやリポジトリへ自己増殖的に拡散する挙動を持つ。C2インフラの追跡耐性を高めるため、Ethereumスマートコントラクトを用いてC2ドメインを動的に取得する手法（デッドドロップ方式）も採用されている。

MicrosoftとWizのセキュリティチームがそれぞれ本キャンペーンの分析とIOC（侵害指標）を公開しており、影響を受けたパッケージは合計で週間数千万〜2億ダウンロード規模に達するとの報告もある。

### 影響範囲

- 影響パッケージ：keyv、cacheable を含む約450種類
- 悪性バージョン数：約2,244件
- 侵入経路：npmメンテナーのGitHubアカウント侵害
- ペイロード：preinstallフック経由の難読化Bunスクリプト、認証情報窃取・自己拡散機能

### セキュリティ上の考察

CI/CD環境における認証情報の自動探索・窃取と、それを用いた自己増殖という組み合わせは、単一パッケージの侵害が短時間でエコシステム全体に波及するリスクを示している。npmのpreinstallスクリプトの実行制御（`--ignore-scripts`等）や、CI環境でのシークレットの最小権限化・短命化が引き続き重要な防御策となる。

---

## 関連記事

なし（新規トピック）
