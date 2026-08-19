# GeoServer 未認証SQLインジェクション ゼロデイ（2026年8月）

## 概要

オープンソース地理空間データ配信プラットフォーム GeoServer に存在する未認証 SQL インジェクション脆弱性（CVSS 9.8、GHSA-mqjf-5f49-2fjh、伝統的なCVE番号は未採番）。OGC Filter 処理時の `jsonArrayContains` 関数（PostGIS DataStore 実装）に起因し、条件次第でRCEに繋がる。2026年8月12日の公開直後から偵察目的の悪用試行が確認されている。

**同一性の判断に役立つ情報：**
- 脆弱性ID: GHSA-mqjf-5f49-2fjh（GitHub Security Advisory）
- 種別: 未認証SQLインジェクション → RCE
- CVSS: 9.8
- 対象製品: GeoServer（PostGIS DataStore使用構成）
- 修正版: 3.0.1 / 2.28.5 / 2.27.6
- 開示日: 2026年8月12日 10:46 UTC

## タイムライン

- [2026-08-17 GeoServer 未認証SQLインジェクション ゼロデイ、RCEに繋がる脆弱性が積極的悪用下に](../articles/2026-08-17-geoserver-sqli-zero-day-rce.md)
