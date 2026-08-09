# keyv/cacheable npmサプライチェーン攻撃「CHAINDROP」（2026年8月）

## 概要

npmの主要キャッシュライブラリ「keyv」のメンテナーGitHubアカウントが侵害され、自己増殖型ワーム「CHAINDROP」（Shai-Huludキャンペーンの新系統、「Mini Shai-Hulud」の後継）が同メンテナーの公開権限下にある全パッケージへ拡散した。cacheable・flat-cache・file-entry-cacheなど月間合計20億ダウンロードに達するパッケージ群が影響を受けた。preinstallフックでBunランタイムを利用した情報窃取プログラムを実行し、npmトークン・GitHub CLIトークン・AWS認証情報・暗号資産ウォレット等を標的とする。

**同一性の判断に役立つ情報：**
- 攻撃発生日: 2026年8月4日
- 起点: keyvメンテナーのGitHubアカウント侵害
- ワーム名: CHAINDROP（Shai-Hulud系統、Mini Shai-Huludの後継）
- 影響パッケージ: keyv, cacheable, flat-cache, file-entry-cache, cacheable-request, cache-manager 等（1,300バージョン超）
- 影響規模: 月間合計約20億ダウンロード
- 手口: preinstallフック → Bunランタイムダウンロード → 728KB難読化情報窃取プログラム実行

## タイムライン

- [2026-08-04 npmの人気キャッシュライブラリkeyv/cacheableが乗っ取り被害、自己増殖ワーム「CHAINDROP」が1300超のパッケージに拡散](../articles/2026-08-09-keyv-cacheable-npm-chaindrop-worm.md)
