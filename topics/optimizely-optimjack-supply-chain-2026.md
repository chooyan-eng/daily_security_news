# Optimizely「OPTIMJACK」サプライチェーン攻撃（2026年11月）

## 概要

A/Bテスト基盤Optimizely Web Experimentationの脆弱性が悪用され、2026年11月16日に顧客プロジェクトのスニペットへ悪性JavaScriptが注入されたサプライチェーン攻撃。通称「OPTIMJACK」。少なくとも178組織（BBC、CNN、Zoom、HSBC、IKEA等）のサイトでカードスキマー、暗号資産クリッパー、iOS向けエクスプロイトキットが配信された。

**同一性の判断に役立つ情報：**
- 被害組織: Optimizely（Web Experimentation）およびその顧客サイト
- 発生: 2026-11-16／Optimizely確認: 2026-11-17
- 原因: Experimentationの新規アカウント作成フローの不具合（詳細未公表）。CVE-2026-132224とする報道あり（未採番とする報道もあり）
- 規模: 1,611スニペット中188件・178組織（下限）、推定約3,400万ページ訪問
- ペイロード: 暗号資産アドレスすり替え、カードスキミング、Cookie/スクリーンショット窃取、iOSエクスプロイトキット Coruna（iOS 13〜17）/ DarkSword（iOS 18）
- 配信元: cdn.optimizely.com（正規証明書）
- 発見者: Scott Helme（Report URI）

## タイムライン

- [2026-11-20 Optimizely経由のサプライチェーン攻撃「OPTIMJACK」、178組織のサイトに悪性JavaScript——カードスキマー・暗号資産クリッパー・iOSエクスプロイトを配信](../articles/2026-11-20-optimizely-optimjack-supply-chain.md)
