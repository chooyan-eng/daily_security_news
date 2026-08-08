# Microsoft、自己拡散型 npm ワーム「ChainDrop」を分析 – 400超パッケージに感染拡大

- **日付**: 2026-08-05
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/08/04/chaindrop-supply-chain-compromise-anatomy-self-propagating-worm/)
- **トピック**: [keyv・cacheable npm サプライチェーン攻撃「Mini Shai-Hulud」（2026年8月）](../topics/keyv-cacheable-npm-mini-shai-hulud-2026.md)
- **分類**: 続報

## 概要

Microsoft Threat Intelligence は、8月4日に始まった keyv・cacheable の乗っ取りを起点とする npm サプライチェーン攻撃を「ChainDrop」と命名し、詳細な技術分析を公開した。侵害は keyv・flat-cache・cache-manager など複数の無関係なパブリッシャーにまたがる400超のパッケージに拡大しており、Deliveroo・OneReach・Ornikar・Picsart・ServiceTitan・Qlik など企業組織のリポジトリにも波及したことが確認された。

## 詳細

### ChainDrop の自己拡散メカニズム

ChainDrop は Bun ベースの重度に難読化された JavaScript ペイロードとして配布される Mini Shai-Hulud 亜種で、npm の preinstall ライフサイクルフックを通じてパッケージインストール完了前に自動実行される。実行後の挙動は以下の通り。

1. 開発者ワークステーションおよび CI/CD 環境から npm・GitHub・クラウド・インフラ関連の認証情報を検索
2. 回収した認証情報で npm・GitHub・AWS・Kubernetes・HashiCorp Vault に対して認証
3. アクセス可能なパッケージ・リポジトリ・ワークフローシークレット・クラウドパラメータ・シークレットストア値を列挙
4. npm 公開トークンを取得後、対象パッケージの最新 tarball をダウンロードし、マルウェアと setup ローダーを挿入
5. preinstall フックを追加し、パッチバージョンをインクリメントして再公開（自己増殖）

### 影響を受けた組織

Deliveroo、OneReach、Ornikar、Picsart、ServiceTitan、Qlik など、keyv/cacheable とは直接関係のない複数の企業のリポジトリでも侵害パッケージが確認されており、単一メンテナーの侵害が業界横断的なサプライチェーンへ波及したことを示している。

### Miasma・Shai-Hulud との関係

Microsoft は ChainDrop を独立した攻撃としてではなく、2026年前半に観測された Shai-Hulud 系自己拡散型ワームの系譜に連なるものと位置づけている。攻撃手法（preinstall フックによるクレデンシャル窃取と自動再公開）は Red Hat npm サプライチェーン攻撃「Miasma」で確認された手口と類似するが、明確に同一のインフラ・パッケージ名前空間ではないため、直接の続報ではなく関連キャンペーンとして扱う。

### 対策

- npm 監査ログでの異常な公開活動の監視
- preinstall/postinstall スクリプトのサンドボックス実行またはブロック
- CI/CD のシークレットスコープを最小化し、短命トークンへ移行

---

## 関連記事

- [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md) - 同系統の preinstall スクリプト悪用による自己拡散型 npm サプライチェーン攻撃
