# Azure CLI パスワードスプレー攻撃「LSHIY」キャンペーン（2026年）

## 概要

Azure CLIを標的とした大規模パスワードスプレー攻撃。2026年6月12〜26日に8100万回超のログイン試行が行われ、64組織・78アカウントが侵害された。攻撃者はLSHIY LLC（AS32167）管理のIPv6レンジを使用し、ROPC OAuth機構でMFAを回避。Huntressが検知。

**同一性の判断に役立つ情報：**
- 攻撃対象: Azure CLI / Microsoft 365アカウント
- 攻撃期間: 2026-06-12〜2026-06-26
- 攻撃元: LSHIY LLC（AS32167、IPv6 2a0a:d683::/32）
- 被害規模: 78アカウント、64組織
- 悪用技術: ROPC（Resource Owner Password Credentials）によるMFAバイパス
- 検知組織: Huntress

## タイムライン

- [2026-07-01 Azure CLIを狙った大規模パスワードスプレー攻撃、8100万回超の試行で78アカウント侵害](../articles/2026-07-01-azure-cli-password-spray-lshiy.md)
