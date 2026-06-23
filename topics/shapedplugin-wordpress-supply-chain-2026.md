# ShapedPlugin WordPress サプライチェーン攻撃（CVE-2026-10735）

## 概要

WordPress プラグイン開発会社 ShapedPlugin のビルド・配布パイプラインが侵害され、プレミアムプラグインの更新ファイルにバックドアが混入したサプライチェーン攻撃。40万件以上のアクティブインストールを持つ同社の有料プラグイン3製品（Product Slider Pro for WooCommerce、Real Testimonials Pro、Smart Post Show Pro）が対象。管理者認証情報と2FAシークレットの窃取、複数のリモートアクセス手段が確立された。

**同一性の判断に役立つ情報：**
- 侵害企業: ShapedPlugin（WordPress プラグイン開発会社）
- CVE: CVE-2026-10735（CVSS 9.8）、CVE-2026-49777（CVSS 10.0）
- 影響製品: Product Slider Pro for WooCommerce（3.5.4未満）、Real Testimonials Pro 3.2.5、Smart Post Show Pro（4.0.2未満）
- 悪意コード混入日: 2026年5月21日
- 開示: 2026年6月11日（Wordfence Threat Intelligence）
- 配布メカニズム: Easy Digital Downloads（EDD）アップデートシステム
- 含有マルウェア: Tiny File Manager 2.6、Adminer 5.2.1、Webシェル、REST APIバックドア

## タイムライン

- [2026-06-23 ShapedPlugin WordPress プロプラグインのサプライチェーン攻撃（CVE-2026-10735）](../articles/2026-06-23-shapedplugin-wordpress-supply-chain.md)
