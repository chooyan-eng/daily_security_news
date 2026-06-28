# OpenAI「Poisoned Tenant」フィッシングキャンペーン（2026年）

## 概要

Push Security が発見した「Poisoned Tenant」攻撃。攻撃者が正規の OpenAI 組織（テナント）作成機能を悪用し、標的企業名を騙る偽 ChatGPT ワークスペースに従業員を招待することで機密情報を収集する。招待メールは OpenAI 公式インフラ（noreply@tm.openai.com）から送信されるためメールセキュリティフィルターをほぼすべてすり抜ける。2026年6月26〜27日に BleepingComputer などが報道し注目を集めた。

**同一性の判断に役立つ情報：**
- 攻撃手法: 偽 OpenAI テナント作成 → 正規招待メール経由でフィッシング
- キャンペーン名: Poisoned Tenant
- 発見: Push Security
- 主な標的セクター: サイバーセキュリティ・テクノロジー企業
- 攻撃者の目的: 従業員が ChatGPT に入力する機密業務情報の収集
- 招待メール送信元: noreply@tm.openai.com（OpenAI 公式、詐称なし）

## タイムライン

- [2026-06-27 OpenAI「Poisoned Tenant」攻撃：偽組織招待で企業従業員を狙うフィッシングキャンペーン](../articles/2026-06-28-openai-poisoned-tenant-phishing.md)
