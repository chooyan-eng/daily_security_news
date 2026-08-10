# ChainDrop npmサプライチェーンワーム攻撃（2026年8月）

## 概要

npmレジストリ上で人気パッケージ「keyv」を起点に感染を広げる自己増殖型マルウェア「ChainDrop」が発見された事案。攻撃者はpreinstallフックでクレデンシャルを窃取し、盗んだトークンを使って`file-entry-cache`・`cache-manager`など関連パッケージへ連鎖的に感染を広げた。被害は1,300以上のパッケージ、月間合計20億ダウンロード規模に達している。

**同一性の判断に役立つ情報：**
- マルウェア名: ChainDrop（自己増殖型npmワーム）
- 感染起点: 「keyv」パッケージ（2026年8月4日公開の悪意あるバージョン）
- 拡散手法: preinstallフックでnpm/GitHub/AWS等の認証トークンを窃取 → 連鎖的にパッケージを汚染
- 関連パッケージ: keyv, file-entry-cache, cache-manager, jaredwray/cacheable, jaredwray/ecto 等
- 被害規模: 1,300以上のパッケージ、月間ダウンロード合計20億件超、2,000以上のアーティファクトを追跡（Socket, Microsoft）
- 特徴: インストール実行せずともautostartフック経由で発動する可能性、インシデント対応時に発動する持続化機構

## タイムライン

- [2026-08-10 自己増殖型npmワーム「ChainDrop」が1,300以上のパッケージに感染、月間20億ダウンロード規模に拡大](../articles/2026-08-10-chaindrop-npm-supply-chain.md)
