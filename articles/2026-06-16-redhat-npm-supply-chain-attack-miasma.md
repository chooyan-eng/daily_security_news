# Red Hat npmパッケージを標的としたサプライチェーン攻撃「Miasma」、32件のパッケージが侵害

- **日付**: 2026-06-16
- **出典**: [Wiz Research Blog](https://www.wiz.io/blog/miasma-supply-chain-attack-targeting-redhat-npm-packages)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 新規

## 概要

2026年6月1日、Wiz Researchが@redhat-cloud-servicesのnpmネームスペース下の複数パッケージに不正な改ざんを発見した（「Miasma」と命名）。週間合計約8万ダウンロードを誇る32件のパッケージがインストール時に自動実行されるマルウェアを含んでいた。RedHatのGitHubアカウントが侵害されてコードが注入されたと推測される。

## 詳細

### 攻撃の経緯

- **2026年6月1日**：Wiz Researchが@redhat-cloud-servicesネームスペースのnpmパッケージに不正な変更を検出
- **2026年6月4日**：Wiz Researchが第2弾の脅威アドバイザリを公開（`binding.gyp`を悪用した新たな攻撃手法）

### 技術的手法

攻撃者はパッケージに以下の改ざんを加えた：

1. **preinstallスクリプト**：パッケージインストール時に自動的に`index.js`（マルウェア）を実行するpreinstallスクリプトを追加
2. **binding.gypの悪用**：第2波ではネイティブモジュールビルド時に使用される`binding.gyp`を通じてマルウェアコードを実行
3. **侵害されたGitHubアカウント経由**：Red HatのGitHub組織内で管理されているパッケージリポジトリに悪意あるコードを注入

### 影響範囲

- 侵害されたパッケージ数：32件以上（第2波を含む）
- @redhat-cloud-servicesの週間ダウンロード数：累計約8万件
- 主にCI/CDパイプラインやクラウド環境でこれらパッケージを使用する開発者・組織が影響を受ける

### 攻撃の目的

マルウェアの主な目的はCI/CDパイプラインのクレデンシャル窃取とクラウド環境へのアクセス権取得と推測されており、大規模なクラウドインフラへのピボット（横展開）が狙いと考えられる。

### 推奨対応

- `@redhat-cloud-services/`ネームスペースのパッケージを使用している場合は直ちに侵害有無を確認
- npm auditおよびSBOM（Software Bill of Materials）を使用した依存関係の検証
- CI/CDパイプラインのシークレット・クレデンシャルをローテーション
- preinstallスクリプトの実行を`--ignore-scripts`フラグで防ぐことを検討
- npmパッケージのハッシュ値（integrity）検証の強化

---

## 関連記事

なし
