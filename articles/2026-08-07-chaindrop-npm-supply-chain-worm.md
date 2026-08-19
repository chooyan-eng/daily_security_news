# 自己拡散型npmワーム「ChainDrop」がkeyv/cacheable系パッケージを汚染 – 440以上のパッケージ・月間20億インストールに影響

- **日付**: 2026-08-07
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/08/04/chaindrop-supply-chain-compromise-anatomy-self-propagating-worm/) / [The Hacker News](https://thehackernews.com/2026/08/n-able-says-attackers-take-over-n.html)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 関連

## 概要

2026年8月4日、自己拡散型のnpmサプライチェーンワーム「ChainDrop」（「Mini Shai-Hulud」の新たな波と位置付け）が発生し、keyv・cacheable名前空間を起点に4時間足らずで444パッケージ・2,212バージョンを汚染した。侵害されたメンテナーのGitHubアカウントとCI/CDパイプラインを悪用し、正規の署名付きで悪性バージョンがnpmレジストリへ公開された。影響を受けたパッケージの週間ダウンロード数は合計5億件超、月間インストール数は20億件を超えるとされる。

## 詳細

### 攻撃の経緯

攻撃者はkeyv・cacheable系の広く使われるNode.jsユーティリティパッケージのメンテナーのGitHubアカウントを侵害し、mainブランチへ悪性コードを直接プッシュ。メンテナー自身のGitHub Actionsパイプラインをトリガーさせてビルド・公開させることで、正規のデジタル署名付きの悪性バージョンをnpmレジストリに配布させた。

### ペイロードの仕組み

開発者やCI/CDシステムが影響を受けたパッケージに対して`npm install`を実行すると、隠された`preinstall`スクリプト（`setup.mjs`）が自動的に起動する。このスクリプトは検知回避のため一時的なBunランタイム実行ファイルをダウンロードし、それを用いて難読化された第2段階ペイロード（`Math_Symbol.js`）を実行する。このペイロードはGitHub Actionsランナーのメモリをダンプして一時的な公開用トークンを窃取する、攻撃的な情報窃取＋自己拡散機能を備えたマルウェアである。

### 規模

4時間足らずで444パッケージ・2,212バージョンを汚染。keyv@6.0.0（週間ダウンロード1.5億件超）、flat-cache@6.1.24（同1.499億件）、file-entry-cache@11.1.6（同1.476億件）などが含まれる。最終的に1,300以上のパッケージ（合計月間20億インストール超）が影響を受けたとされる。

### その後の動き

2026年8月4日、攻撃者はマルウェア本体を更新することなく、単一のEthereumトランザクションを通じてC2インフラ全体を静かに再構成したことが観測されている。ブロックチェーン上のデータを利用した検知回避・耐障害性の高いC2手法として注目される。

### 対策

1. keyv・cacheable関連パッケージおよびその依存関係を利用しているプロジェクトの依存ツリーを緊急点検
2. CI/CDのnpmトークン・GitHub Actionsのシークレットをローテーション
3. `preinstall`/`postinstall`スクリプトの実行を制限する設定（`--ignore-scripts`等）の導入検討
4. サプライチェーンセキュリティツールによる継続的な依存関係監視

---

## 関連記事

- [Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化](../articles/2026-06-16-shai-hulud-supply-chain-worm-320-packages.md) - 同系統の自己拡散型npmワームの先行事例（Shai-Hulud系譜）
- [Shai-Hulud サプライチェーン攻撃 - npm/PyPIで170+パッケージ汚染、SLSA Build Level 3も突破](../articles/2026-06-19-shai-hulud-npm-pypi-third-wave.md) - 「Mini Shai-Hulud」呼称の先行する波
