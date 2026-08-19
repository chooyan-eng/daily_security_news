# BdThemes WordPressプラグイン サプライチェーン攻撃（2026年8月）

## 概要

BdThemes製の複数WordPressプラグインを狙ったサプライチェーン攻撃。プラグイン本体のソースコードではなく、ベンダーが配信する外部JSONデータを改ざんし、管理者の認証済みセッションを悪用して不正管理者アカウントを作成、Webシェルを設置する手口。Wordfence Threat Intelligenceが2026年8月7日に通報を受け調査、キャンペーンの開始は少なくとも6月23日まで遡ることが判明。影響を受けた7プラグインは8月7〜8日にWordPress.orgディレクトリで公開停止された。

**同一性の判断に役立つ情報：**
- 対象: BdThemes製WordPressプラグイン群（7プラグイン）
- 手法: 外部JSON改ざんによるサプライチェーン攻撃（ソースコード自体は無改ざん）
- ペイロード: `w2.js`（管理者セッション悪用による不正アカウント作成）
- C2/配信先ドメイン: `ia-cdn[.]com`
- 不正アカウント命名規則: `bd_`＋ホスト名由来のBase36ハッシュ
- 通報日: 2026年8月7日（Wordfence Threat Intelligence）
- キャンペーン開始推定: 2026年6月23日
- プラグイン公開停止: 2026年8月7〜8日
- 侵害元: BdThemes（WordPressプラグイン開発元）上流インフラ
- 脆弱性の根本原因: Biggop Library（2026年3月混入のXSS）
- 悪用コンポーネント: Biggopti（プロモーションバナー配信システム）
- 影響プラグイン: Element Pack、Prime Slider、Pixel Gallery、Ultimate Post Kit、Ultimate Store Kit、Live Copy Paste、Smart Admin Assistant
- 攻撃内容: 不正管理者アカウント作成、Webシェル（emer-run.php）設置
- 検知開始日: 2026-08-07（Wordfence WAF）
- ベンダー: BdThemes（Element Pack、Prime Slider、Ultimate Post Kit等のWordPressプラグイン提供元）
- 検知日: 2026年8月7日（Wordfence）
- 手口: 上流インフラ侵害によるJSONフィード改ざん → XSS → 管理者セッション悪用で不正管理者作成
- 永続化手段: 偽装プラグイン経由のWebシェル（emer-run.php）
- 関連する過去の攻撃: Advanced Responsive Video Embedder（CVE-2026-18072）、OptinMonster

## タイムライン

- [2026-08-12 BdThemes、複数WordPressプラグインのJSONフィード改ざんでXSS経由の不正管理者アカウント作成・Webシェル設置が発覚](../articles/2026-08-12-bdthemes-wordpress-supply-chain.md)
- [2026-08-11 BdThemes製WordPressプラグイン群でサプライチェーン攻撃、偽装JSONで不正管理者アカウントを作成](../articles/2026-08-16-bdthemes-wordpress-supply-chain.md)
- [2026-08-11 BdThemes WordPress サプライチェーン攻撃 — 汚染JSONフィードで不正管理者アカウントを自動作成](../articles/2026-08-11-bdthemes-wordpress-supply-chain.md)
