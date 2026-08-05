# ChainDrop npmサプライチェーンワーム（2026年8月）

## 概要

npmの人気パッケージ「keyv」「cacheable」等を起点に拡散した自己増殖型クレデンシャル窃取ワーム「ChainDrop」によるサプライチェーン攻撃キャンペーン。npmメンテナーのGitHubアカウント侵害を起点に、preinstallフック経由でBunベースの難読化ペイロードを配布し、CI/CD環境の認証情報を窃取・自己拡散させる。同一キャンペームはOpen VSXマーケットプレイスでの「Evil Twin」型悪性拡張機能77件の配布にも関与している。

**同一性の判断に役立つ情報：**
- キャンペーン名: ChainDrop（別名 keyv-shai-hulud、Mini Shai-Hulud亜種を使用）
- 起点: npmメンテナーのGitHubアカウント侵害
- 影響パッケージ: keyv、cacheable等 約450種類、悪性バージョン約2,244件
- 手口: npm preinstallフック → Bun難読化ペイロード → 認証情報窃取 → 自己拡散、Ethereumスマートコントラクト経由のC2デッドドロップ
- 関連キャンペーン: Open VSX「Evil Twin」拡張機能77件（2026年7月26日〜8月1日アップロード、8月3日削除）
- 悪用開始: 2026年8月4日UTC10:53頃

## タイムライン

- [2026-08-04 「ChainDrop」自己増殖型npmワーム、keyv・cacheable等450パッケージ・2,200超のバージョンに感染](../articles/2026-08-04-chaindrop-npm-worm.md)
- [2026-08-05 Open VSXで「Evil Twin」型の悪性拡張機能77件を検出・削除、ChainDropキャンペーンの一部と判明](../articles/2026-08-05-openvsx-evil-twin-extensions.md)
