# Optimizely Web Experimentation 侵害によるWebサプライチェーン攻撃（2026年11月）

## 概要

A/Bテスト・実験基盤Optimizely Web Experimentationが2026年11月16日に侵害され、顧客サイトへ悪性JavaScriptが配信されたWebサプライチェーン攻撃。Report URIのScott Helme氏が発見。「OPTIMJACK」と呼ぶベンダーもある。

**同一性の判断に役立つ情報：**
- 原因: アカウントサインアップ処理の脆弱性により顧客管理者になりすまし、Project JavaScriptを改ざん（CVE未採番）
- 規模: 1,611スニペット中188個が汚染、少なくとも178組織（Zoom、BBC、CNN、Fox News、Salesforce、GitLab等）
- ペイロード: 暗号資産クリッパー、カードスキマー、Cookie・スクリーンショット窃取、iOS向けエクスプロイトキットCoruna／DarkSword
- 配信期間: 11月16日の約17時間（報道）。9月にトルコのサイトで先行観測

## タイムライン

- [2026-11-18 Optimizelyのサインアップ処理の脆弱性を悪用、178組織のWebサイトに悪性JavaScript CNN・BBC・SalesforceなどでカードスキマーやiOSエクスプロイトを配信](../articles/2026-11-18-optimizely-web-experimentation-supply-chain.md)
