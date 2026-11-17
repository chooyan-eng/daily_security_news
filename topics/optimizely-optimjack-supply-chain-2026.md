# Optimizely Web Experimentation スクリプト改ざん「OPTIMJACK」（2026年11月）

## 概要

A/BテストSaaS「Optimizely Web Experimentation」のアカウントサインアップフローの脆弱性が悪用され、顧客プロジェクトの「Project JavaScript」に悪性コードが注入されたサプライチェーン攻撃。StepSecurityが「OPTIMJACK」と命名。2026年11月16日発覚、11月17日（UTC）封じ込め。

**同一性の判断に役立つ情報：**
- 影響: 178組織（CNN、BBC、Zoom、Salesforce、Fox News、HSBC、Air France-KLMなど）
- 配信元: cdn.optimizely.com の正規スニペット／2段目取得先: `1688360[.]cc/track.js`
- ペイロード: カードスキマー、暗号資産クリッパー、iOSエクスプロイトキット
- 厳格なCSP（script-src / connect-src）を設定したサイトは被害を免れた

## タイムライン

- [2026-11-17 「OPTIMJACK」Optimizely経由で178組織のサイトに悪性JavaScript配信](../articles/2026-11-17-optimizely-optimjack-supply-chain.md)
