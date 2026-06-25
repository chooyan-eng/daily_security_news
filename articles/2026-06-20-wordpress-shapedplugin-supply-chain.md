# WordPress ShapedPlugin プレミアムプラグイン サプライチェーン攻撃（CVE-2026-10735）

- **日付**: 2026-06-20
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/shapedplugin-update-flow-hacked-to-infect-wordpress-sites/)
- **トピック**: [WordPress Awesome Motive CDNサプライチェーン攻撃（2026年6月）](../topics/wordpress-awesome-motive-cdn-attack-2026.md)
- **分類**: 関連

## 概要

WordPress プレミアムプラグイン開発会社 ShapedPlugin のビルド・配布パイプラインが侵害され、3つの有料プラグインにバックドアが注入された。2026年5月21日から6月10日にかけて被害者に悪意あるアップデートが配布されており、攻撃者は管理者認証情報・2FA シークレット・リモートアクセス手段を奪取した。CVE-2026-10735として追跡されている。

## 詳細

### インシデント概要

ShapedPlugin は WordPress 向けプレミアムプラグインを開発する企業で、主に WooCommerce 向けの有料プラグインを販売している。2026年6月に、同社の有料プラグイン配布システムが侵害されたことが明らかになった。

### 攻撃の仕組み

攻撃者は ShapedPlugin の Easy Digital Downloads（EDD）ベースのアップデート配信システムに侵入し、プレミアムプラグインのビルドパッケージに悪意あるコードを注入した。悪意あるアップデートは公式の更新システムを通じて正規の購入者に配布された。

### 侵害されたプラグインと期間

影響を受けた有料プラグイン（3件）：
- **Product Slider Pro for WooCommerce**（3.5.4 未満）
- **Real Testimonials Pro**（3.2.5）
- **Smart Post Show Pro**（4.0.2 未満）

バックドアが注入された期間：2026年5月21日〜6月10日（約20日間）

### バックドアの機能

注入されたバックドアが提供する攻撃者の機能：
- 管理者認証情報の窃取（ユーザー名・パスワード）
- 二要素認証（2FA）シークレットの窃取
- 複数のリモートアクセス手段の設置
- WordPress サイトへの持続的なアクセス権の確保

### CVE 情報

- **CVE-2026-10735**: メインの追跡 CVE（WordPress がこのインシデントに付与）
- **CVE-2026-49777**: 重複として提出された CVE

### 対応状況

ShapedPlugin はセキュリティ侵害を認め、影響を受けたバージョンをリポジトリから削除した。2026年4月〜6月の間に ShapedPlugin プレミアムプラグインをインストールまたは更新した WordPress サイトは侵害されている可能性がある。

### 推奨対応

1. 影響を受けるバージョンを使用している場合は、即時アップデートまたは削除する
2. WordPress サイトを完全スキャンして不審なファイル・データベースエントリを確認する
3. すべての WordPress 管理者パスワードを変更する
4. 2FA シークレットをリセットする
5. サーバーのアクセスログを調査して侵害の痕跡を確認する

---

## 関連記事

- [WordPress Awesome Motive CDNサプライチェーン攻撃 - 複数の人気プラグインに悪意あるコードが注入](../articles/2026-06-16-wordpress-awesome-motive-cdn-attack.md) - 同じ WordPress プレミアムプラグインエコシステムを標的にしたサプライチェーン攻撃
