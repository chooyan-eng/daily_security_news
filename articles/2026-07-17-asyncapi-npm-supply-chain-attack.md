# npmパッケージ「@asyncapi」がサプライチェーン攻撃で侵害 ― import時に悪意あるローダーを実行、週200万DLに影響

- **日付**: 2026-07-17
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/07/15/unpacking-asyncapi-npm-supply-chain-compromise-import-time-payload-delivery/) / [Security Affairs](https://securityaffairs.com/195395/security/asyncapi-npm-supply-chain-attack-malware-injected-into-packages-with-2-million-weekly-downloads.html)
- **トピック**: [@asyncapi npmサプライチェーン攻撃（2026年7月）](../topics/asyncapi-npm-supply-chain-2026.md)
- **分類**: 新規

## 概要

Microsoft Threat Intelligenceは2026年7月14日、npmの@asyncapi organizationが協調的なサプライチェーン攻撃で侵害されたと報告した。4つのパッケージにわたる5バージョンが悪意あるローダーを注入された状態で再公開され、@asyncapi/specsが多数のAsyncAPI関連ツールの推移的依存関係であるため、開発者端末・CI/CDパイプライン・コンテナビルド・本番サービスに影響が及んだ。従来のpostinstallフック型と異なり、モジュールロード（import/require）時にペイロードが実行される点が特徴で、週間200万ダウンロード規模のパッケージ群が対象となった。

## 詳細

### 攻撃の概要

2026年7月14日、Microsoft Threat Intelligenceは npm の @asyncapi organization に対する協調的なサプライチェーン侵害を特定した。4つのパッケージ名にわたる5つのバージョンが、悪意あるローダーコードを注入された状態で再公開されていた。

### 技術的特徴：import時実行

これまで多く報告されてきたnpmサプライチェーン攻撃は、パッケージインストール時に自動実行される`postinstall`フックを悪用する手口が主流だった。しかし今回のキャンペーンでは、モジュールがロードされる（`import`／`require`される）タイミングでペイロードが実行される点が特徴で、検知や封じ込めがより困難になっている。

### 影響範囲

@asyncapi/specs は多数の AsyncAPI 関連ツーリングパッケージの推移的依存関係（transitive dependency）であるため、直接このパッケージをインストールしていない開発者・組織にも影響が波及した。影響を受けた領域は、開発者ワークステーション、CI/CDパイプライン、コンテナビルドプロセス、さらに本番稼働中のサービスにまで及ぶとされる。侵害されたパッケージ群は合計で週間約200万ダウンロード規模とされている。

### 同時期の他の npm サプライチェーン攻撃

同じ7月には、jscrambler npmパッケージが盗まれた公開用認証情報を使って侵害され（7月11日）、開発者端末・CI/CDパイプラインから認証情報を窃取する隠しネイティブバイナリが仕込まれる事案も発生している。npmエコシステムを狙った同種の攻撃が短期間に連続して発生しており、業界全体でnpm v12における`postinstall`スクリプトのデフォルト無効化など対策強化が進められている。

### 対策推奨

- @asyncapi 関連パッケージを直接・間接的に利用しているプロジェクトは、ロックファイルを確認し侵害バージョンを排除
- CI/CDパイプラインにおける依存関係のハッシュ検証・SBOM管理の徹底
- import時に自動実行されるコードを検知するランタイム監視の導入検討

---

## 関連記事

なし（新規トピック）
