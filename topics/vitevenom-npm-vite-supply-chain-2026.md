# ViteVenom：Vite npm サプライチェーン攻撃（2026年）

## 概要

フロントエンドビルドツール Vite のエコシステムを標的とした npm サプライチェーン攻撃。`@vitejs/*` 名前空間を模したスコープ付きパッケージ7件を通じて、Tron・Aptos・Binance Smart Chain にまたがる4層ブロックチェーンベース C2 インフラで RAT（リバースシェル・クレデンシャル窃取・ファイル窃取・バックドア機能）を配布する。既存キャンペーン「ChainVeil」の拡張形であり、脅威アクター「SuccessKey」に帰属。

**同一性の判断に役立つ情報：**
- キャンペーン名: ViteVenom（Checkmarx 命名）
- 関連キャンペーン: ChainVeil（先行するタイポスクワッティング型攻撃）
- 脅威アクター: SuccessKey
- 対象: `@vitejs/*` スコープを模したパッケージ7件
- C2 手法: Tron・Aptos・Binance Smart Chain にまたがる4層ブロックチェーン C2
- パッケージ公開期間: 2026-06-29〜2026-07-03

## タイムライン

- [2026-07-19 「ViteVenom」— Vite エコシステムを狙う悪意ある npm パッケージ7件、ブロックチェーン C2 で RAT を配布](../articles/2026-07-19-vitevenom-npm-vite-supply-chain.md)
