# BdThemes、複数WordPressプラグインのJSONフィード改ざんでXSS経由の不正管理者アカウント作成・Webシェル設置が発覚

- **日付**: 2026-08-12
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/bdthemes-plugins-supply-chain-hack-creates-rogue-wordpress-admins/), [GBHackers](https://gbhackers.com/wordpress-supply-chain-attack-exploits-bdthemes-plugins/)
- **トピック**: [BdThemes WordPress プラグイン サプライチェーン攻撃（2026年8月）](../topics/bdthemes-wordpress-supply-chain-2026.md)
- **分類**: 新規

## 概要

プレミアムWordPressプラグイン開発元BdThemesの上流インフラが侵害され、管理ダッシュボードが参照するリモートJSONフィードに悪意あるコードが注入された。Element Pack、Prime Slider等、同社の複数プラグインに影響し、正規管理者のセッションを悪用して不正な管理者アカウントを作成、Webシェルを設置する攻撃が8月7日頃から観測されている。

## 詳細

### 脆弱性の根本原因

攻撃の起点は、2026年3月にBdThemesのJSONレスポンス解析コードに混入していたコーディング上の欠陥。同社プラグイン群で共通利用される内部プロモーションバナーシステム「Biggopti」（ベンダーのAPIサーバーからバナー情報を取得し、顧客のWordPress管理画面に表示するコンポーネント）で使用される「Biggop Library」にクロスサイトスクリプティング（XSS）脆弱性が存在していた。

### 攻撃手法

攻撃者はBdThemes側のインフラを侵害し、Biggoptiが参照する静的JSONデータストリームに悪意あるJavaScriptを混入させた。このJavaScriptは、WordPress管理画面を閲覧している正規管理者の認証済みセッションを悪用し、不正な管理者アカウントを作成する。さらに追加ペイロード（w2.js）が偽のプラグインをインストールする形でWebシェル（emer-run.php）を設置し、永続的なアクセス経路を確立する。

### 影響を受けるプラグイン

Biggoptiコンポーネントを利用するBdThemes製の以下のプラグインが影響を受ける：Element Pack、Prime Slider、Pixel Gallery、Ultimate Post Kit、Ultimate Store Kit、Live Copy Paste、Smart Admin Assistant。

### 検知と対応状況

WordPressセキュリティ企業Defiantは、自社のWordfence WAFを通じて8月7日から本攻撃の検知を開始した。該当プラグインのWordPress.org上の掲載ページは、8月7日または8日時点で「全面レビュー」を理由に一時非表示となっている。

### 対策

- 該当するBdThemes製プラグインを利用している場合、修正版の提供状況を確認し速やかに更新
- 管理画面のユーザー一覧を確認し、心当たりのない管理者アカウントがないか点検
- `emer-run.php` 等、見慣れないファイルがサーバー上に設置されていないか確認
- WAF（Wordfence等）のシグネチャを最新化し、本攻撃パターンの検知を有効化

---

## 関連記事

なし（新規トピック）
