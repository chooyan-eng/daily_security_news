# BdThemes WordPress プラグイン サプライチェーン攻撃（2026年8月）

## 概要

プレミアムWordPressプラグイン開発元BdThemesの上流インフラが侵害され、複数プラグインが共通利用する内部プロモーションシステム「Biggopti」が参照するJSONフィードに悪意あるコードが混入された事案。2026年3月に混入したXSS脆弱性（Biggop Library）が悪用の起点となり、正規管理者のセッションを使って不正な管理者アカウントを作成、Webシェル（emer-run.php）を設置する。2026年8月7日からWordfence WAFで検知され始めた。

**同一性の判断に役立つ情報：**
- 侵害元: BdThemes（WordPressプラグイン開発元）上流インフラ
- 脆弱性の根本原因: Biggop Library（2026年3月混入のXSS）
- 悪用コンポーネント: Biggopti（プロモーションバナー配信システム）
- 影響プラグイン: Element Pack、Prime Slider、Pixel Gallery、Ultimate Post Kit、Ultimate Store Kit、Live Copy Paste、Smart Admin Assistant
- 攻撃内容: 不正管理者アカウント作成、Webシェル（emer-run.php）設置
- 検知開始日: 2026-08-07（Wordfence WAF）

## タイムライン

- [2026-08-12 BdThemes、複数WordPressプラグインのJSONフィード改ざんでXSS経由の不正管理者アカウント作成・Webシェル設置が発覚](../articles/2026-08-12-bdthemes-wordpress-supply-chain.md)
