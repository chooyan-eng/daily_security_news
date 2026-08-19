# Azure CLI パスワードスプレーキャンペーン「LSHIY」（2026年）

## 概要

2026年6月12日〜26日にHuntressが観測した、Microsoft 365環境を狙う大規模パスワードスプレーキャンペーン。8,100万回超のログイン試行により64組織・78アカウントが侵害された。Azure CLI経由のROPC OAuth認証を悪用し、条件付きアクセスの設定不備によりMFAを回避する手口。発信元IPレンジからLSHIY LLC（AS32167）と紐付けられている。

**同一性の判断に役立つ情報：**
- キャンペーン名（通称）: LSHIY
- 観測元: Huntress
- 観測期間: 2026年6月12日〜26日
- 規模: ログイン試行8,100万回超、侵害78アカウント／64組織
- 攻撃手法: Azure CLI経由のROPC（Resource Owner Password Credentials）OAuth認証悪用
- MFA回避要因: 条件付きアクセスポリシーの設定不備（アプリ限定適用・グループ限定適用・レポートのみモード）
- 発信元: LSHIY LLC（AS32167）保有のIPv6アドレス範囲
- エスカレーション日: 2026年6月22日（1日で23組織・30アカウント侵害）
- キャンペーン名: LSHIY パスワードスプレー攻撃
- 発信元: LSHIY LLC（AS32167）管理のIPv6アドレス範囲
- 観測期間: 2026-06-12 〜 2026-06-26
- 攻撃規模: 8100万回超のログイン試行
- 被害: 64組織・78アカウント（Microsoft/Azure）
- 悪用手法: ROPC（Resource Owner Password Credentials）によるCAP/MFAバイパス
- 発見: Huntress
- 攻撃対象: Azure CLI / Microsoft 365アカウント
- 攻撃期間: 2026-06-12〜2026-06-26
- 攻撃元: LSHIY LLC（AS32167、IPv6 2a0a:d683::/32）
- 被害規模: 78アカウント、64組織
- 悪用技術: ROPC（Resource Owner Password Credentials）によるMFAバイパス
- 検知組織: Huntress
- キャンペーン期間: 2026年6月12日〜26日
- 攻撃手法: Azure CLI経由のOAuth ROPCフロー悪用、MFA回避
- 侵害結果: 64組織・78アカウント
- 攻撃元: LSHIY LLC保有のIPv6アドレス範囲（AS32167）
- 報告元: Huntress

## タイムライン

- [2026-07-07 Microsoft 365 標的に8,100万回超のパスワードスプレー攻撃、Azure CLI経由でMFAを回避](../articles/2026-07-07-azure-cli-password-spray-lshiy.md)
- [2026-07-05 Azure CLIを狙った8100万回超のパスワードスプレー攻撃、78アカウントが侵害](../articles/2026-07-05-azure-cli-password-spray-81million.md)
- [2026-07-03 Microsoft 365に8100万回超のパスワードスプレー攻撃、Azure CLIのROPCフローでMFAを回避](../articles/2026-07-03-microsoft-365-password-spray-ropc.md)
- [2026-07-01 Azure CLIを狙った大規模パスワードスプレー攻撃、8100万回超の試行で78アカウント侵害](../articles/2026-07-01-azure-cli-password-spray-lshiy.md)
