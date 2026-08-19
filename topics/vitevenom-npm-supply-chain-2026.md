# ViteVenom npm サプライチェーン攻撃（2026年7月）

## 概要

Vite フロントエンドツールエコシステムを標的とした npm サプライチェーン攻撃「ViteVenom」。`@vitejs/*` 名前空間を模倣した7個の悪意あるパッケージが、Tron・Aptos・Binance Smart Chain にまたがるブロックチェーンベースのC2インフラを用いてRATを配信する。既知キャンペーン「ChainVeil」の拡張版とされ、脅威アクター「SuccessKey」に帰属。Checkmarxが発見・命名。

**同一性の判断に役立つ情報：**
- 攻撃名: ViteVenom（ChainVeilの拡張）
- 脅威アクター: SuccessKey
- 対象: npm、`@vitejs/*` 名前空間を模倣したパッケージ7個
- パッケージ公開期間: 2026年6月29日〜7月3日
- C2手法: Tron・Aptos・Binance Smart Chain上のトランザクションデータ
- 発見: Checkmarx
- 実行タイミング: インストール時ではなくインポート時

## タイムライン

- [2026-07-18 ViteVenom：Vite エコシステムを標的としたブロックチェーン C2 npm サプライチェーン攻撃](../articles/2026-07-18-vitevenom-npm-supply-chain.md)
