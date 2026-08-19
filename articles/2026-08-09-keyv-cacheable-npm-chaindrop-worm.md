# npmの人気キャッシュライブラリkeyv/cacheableが乗っ取り被害、自己増殖ワーム「CHAINDROP」が1300超のパッケージに拡散

- **日付**: 2026-08-04
- **出典**: [Elastic Security Labs](https://www.elastic.co/security-labs/shai-hulud-chaindrop-npm-supply-chain) / [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/08/04/chaindrop-supply-chain-compromise-anatomy-self-propagating-worm/)
- **トピック**: [npm keyv/cacheable サプライチェーンワーム（2026年8月）](../topics/npm-keyv-cacheable-worm-2026.md)
- **分類**: 続報
## 概要

npmの主要なキャッシュ・ストレージライブラリ「keyv」のメンテナーアカウントが侵害され、自己増殖型ワーム「CHAINDROP」（Shai-Huludキャンペーンの新系統）が、keyvが公開権限を持つ全パッケージへ自動的にバックドアを仕込んだ。月間ダウンロード数で合計20億回に達する1,300以上のパッケージバージョンが影響を受け、cacheable・flat-cache・file-entry-cacheなど広く使われる関連パッケージも巻き込まれた。

## 詳細

### 攻撃の経緯

2026年8月4日、攻撃者はkeyvのメンテナーのGitHubアカウントを侵害し、そのアクセス権を用いてkeyv本体を含むモノレポ全体をトロイの木馬化した。ここに埋め込まれた自己増殖ワーム「CHAINDROP」は、窃取したnpm認証情報を使って、当該メンテナーが公開権限を持つ他の全パッケージへも自動的にバックドアを展開する仕組みを持つ。

### 規模

影響を受けたパッケージは1,300バージョン超、合計で月間20億ダウンロードに相当する。特にkeyv単体で月間6億超、flat-cacheが約5.8億、cacheable-requestが1.37億超、cacheableが3,000万超、cache-managerが1,600万超のダウンロード数を持ち、Node.jsエコシステムの広範囲に影響が及んだ。

### 攻撃手法

CHAINDROPは、以前確認された「Mini Shai-Hulud」の後継にあたるペイロードで、パッケージのインストール前に実行される `preinstall` フックを追加し、Bunランタイムをダウンロードした上で728KBの難読化された情報窃取プログラムを実行する。この窃取プログラムは `.npmrc` トークン、GitHub CLIトークン、AWS認証情報、Vaultトークン、Kubernetes設定ファイル、暗号資産ウォレットなどを標的とする。

### 対応

Node.jsを利用する組織は、依存関係を直ちに見直し、影響を受けたシステム上の認証情報はすべて侵害された可能性があるものとして再発行するなどの対応が求められている。npmエコシステムにおけるメンテナーアカウント乗っ取りを起点とした自己増殖型サプライチェーン攻撃は、2025年後半のShai-Huludワーム以降、同種の手口が繰り返し発生しており、公開鍵署名やパッケージ公開時の多要素認証強制といった構造的対策の必要性が改めて指摘されている。

---

## 関連記事

なし（新規トピック）
