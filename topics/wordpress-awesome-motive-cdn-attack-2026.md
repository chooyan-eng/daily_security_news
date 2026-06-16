# WordPress Awesome Motive CDNサプライチェーン攻撃（2026年6月）

## 概要

WordPressプラグイン大手Awesome Motiveが開発するOptinMonster・TrustPulse・PushEngageのCDNホスト型JavaScriptが改ざんされたサプライチェーン攻撃（2026年6月12〜14日）。UpdraftPlusプラグインの脆弱性を経由してAwesome MotiveのマーケティングサーバーからCDN APIキーを窃取し、SDKファイルに悪意あるコードを注入。管理者ログイン中のWordPressサイトに読み込まれると、不正な管理者アカウントを自動作成し秘匿バックドアをインストールする。3製品合計で1,200万件以上のWordPressサイトに影響する可能性があった。

**同一性の判断に役立つ情報：**
- 攻撃対象: OptinMonster・TrustPulse・PushEngage（いずれもAwesome Motive製）
- 侵害期間: 2026年6月12日〜2026年6月14日
- 悪用された脆弱性: UpdraftPlus WordPress プラグインの既知の脆弱性
- 影響サイト数: 120万以上（OptinMonster利用分）
- 攻撃手法: CDNホスト型JS改ざん（ブラウザサイド攻撃、SRI未使用）

## タイムライン

- [2026-06-16 WordPress大手プラグイン（OptinMonster/PushEngage）のCDNサプライチェーン攻撃、120万サイトに影響](../articles/2026-06-16-wordpress-optinmonster-cdn-supply-chain.md)
