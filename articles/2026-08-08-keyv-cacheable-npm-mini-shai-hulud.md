# keyv・cacheable 名前空間の npm パッケージが乗っ取り被害 – 月間20億ダウンロード規模の「Mini Shai-Hulud」型サプライチェーン攻撃

- **日付**: 2026-08-04
- **出典**: [Wiz Blog](https://www.wiz.io/blog/keyv-and-cacheable-npm-supply-chain-attack)
- **トピック**: [npm keyv/cacheable サプライチェーンワーム（2026年8月）](../topics/npm-keyv-cacheable-worm-2026.md)
- **分類**: 続報
## 概要

2026年8月4日、npm の人気キャッシュライブラリ keyv・cacheable のメンテナーである Jared Wray 氏の GitHub アカウントが乗っ取られ、10件のコアパッケージに悪意あるバージョンが公開された。攻撃者は正規の GitHub Actions 経由で署名済みリリースを発行したため、provenance 検証をすり抜けた。影響パッケージの月間合計ダウンロード数は20億件超に及び、preinstall スクリプトが認証情報を窃取する。

## 詳細

### 侵害の経緯

攻撃者は keyv・cacheable のメンテナー Jared Wray 氏の GitHub アカウントを乗っ取り、main ブランチに悪意あるファイルを直接プッシュした上で、即座に新しいリリースをカットした。この手口により、悪意あるバージョンは GitHub Actions によって正規に署名された provenance 付きで npm に公開され、サプライチェーンの信頼性検証を通過してしまった。

### マルウェアの挙動

侵害されたパッケージには悪意ある preinstall フック（`setup.mjs`）が仕込まれており、インストール時に以下を実行する。

1. スタンドアロンの Bun ランタイムをダウンロード
2. 難読化された第2段階のペイロードを実行
3. 開発者ワークステーションおよび CI/CD 環境から npm・GitHub・AWS・HashiCorp Vault の認証情報を収集
4. 窃取した認証情報を使い、到達可能な他のパッケージを改変して再公開（自己拡散）

### 被害規模

- 直接侵害: keyv・cacheable 名前空間の少なくとも10パッケージ
- 波及後: 434パッケージ・1,381バージョンが侵害確認済み（Socket.dev 調査時点）
- 影響ダウンロード数: 合計月間20億件超

### 攻撃者の分類

Wiz はこのペイロードを「Mini Shai-Hulud」ファミリーに分類し、2026年前半に確認された TeamPCP キャンペーンおよび @antv キャンペーンとの類似性を指摘している。自己増殖型ワームの詳細な技術分析は、Microsoft が公開した「ChainDrop」分析（関連記事参照）で補完されている。

### 対策

- keyv・cacheable および関連パッケージを最新の正規バージョンに固定
- CI/CD 環境の npm・GitHub・クラウド認証情報のローテーション
- lockfile の diff 監視、preinstall スクリプトを含むパッケージの自動実行を制限するポリシーの導入

---

## 関連記事

なし（新規トピック）
