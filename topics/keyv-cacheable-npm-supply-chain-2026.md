# keyv/cacheable npmサプライチェーン攻撃（2026年8月）

## 概要

npmの人気キャッシュライブラリ「keyv」および関連パッケージ「cacheable」が、GitHubメンテナーアカウントの侵害を発端に乗っ取られたサプライチェーン攻撃。悪意あるpreinstallフックを含む`keyv@6.0.0`等11件のリリースが公開され、窃取した認証情報を使ってワームのように`file-entry-cache`・`cache-manager`など関連パッケージへ拡散。月間20億インストール超のエコシステムに影響。

**同一性の判断に役立つ情報：**
- 対象パッケージ: keyv、cacheable、file-entry-cache、cache-manager 他
- 侵害発端: GitHubメンテナーアカウントの侵害
- 悪意あるリリース公開: 2026年8月4日 09:35 UTC（keyv@6.0.0）
- 悪意あるリリース数: keyv関連11件
- 攻撃手法: preinstallフックによる難読化ローダー→第二段階ペイロードでnpm/GitHub/AWS認証情報を窃取
- 拡散規模: 868件以上のパッケージ、月間20億インストール超に影響

## タイムライン

- [2026-08-15 npmパッケージ keyv/cacheable が乗っ取り被害 – ワーム化し868超のパッケージに拡散](../articles/2026-08-15-keyv-cacheable-npm-supply-chain.md)
