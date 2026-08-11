# BdThemes WordPress サプライチェーン攻撃（2026年8月）

## 概要

WordPress向けプラグインベンダー BdThemes の上流インフラが侵害され、管理画面に配信されるJSONフィードの改ざんにより不正管理者アカウントとWebシェルが自動作成される攻撃が確認された。Wordfenceが2026年8月7日に検知。

**同一性の判断に役立つ情報：**
- ベンダー: BdThemes（Element Pack、Prime Slider、Ultimate Post Kit等のWordPressプラグイン提供元）
- 検知日: 2026年8月7日（Wordfence）
- 手口: 上流インフラ侵害によるJSONフィード改ざん → XSS → 管理者セッション悪用で不正管理者作成
- 永続化手段: 偽装プラグイン経由のWebシェル（emer-run.php）
- 関連する過去の攻撃: Advanced Responsive Video Embedder（CVE-2026-18072）、OptinMonster

## タイムライン

- [2026-08-11 BdThemes WordPress サプライチェーン攻撃 — 汚染JSONフィードで不正管理者アカウントを自動作成](../articles/2026-08-11-bdthemes-wordpress-supply-chain.md)
