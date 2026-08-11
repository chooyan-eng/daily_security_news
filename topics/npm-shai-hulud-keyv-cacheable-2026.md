# npmサプライチェーン攻撃「Shai-Hulud」ワーム（2026年8月）

## 概要

npmの人気キャッシュ系パッケージ（keyv、cacheable、flat-cache、file-entry-cache等）がメンテナのGitHubアカウント侵害を起点に汚染され、認証情報窃取・自己増殖型の「Shai-Hulud」ワームが月間ダウンロード数20億件超の規模で拡散した。

**同一性の判断に役立つ情報：**
- マルウェア名: Shai-Hulud（ワーム、認証情報窃取＋自己増殖）
- 侵害起点: keyvメンテナのGitHubアカウント侵害
- 影響パッケージ: keyv、cacheable、flat-cache、file-entry-cache等、汚染バージョン1,300超
- 発覚日: 2026年8月4日
- 手口: 悪意あるプリインストールフック（setup.mjs）→Bunランタイム経由の第2段階ペイロード→クラウド/CI認証情報窃取→他パッケージへの再感染
- 規模: 影響パッケージの月間インストール数合計20億件超

## タイムライン

- [2026-08-11 npmサプライチェーン攻撃「Shai-Hulud」ワーム — keyv/cacheable等1,300超のパッケージバージョンが汚染](../articles/2026-08-11-npm-shai-hulud-keyv-cacheable.md)
