# Azure CLI パスワードスプレー攻撃キャンペーン「LSHIY」（2026年）

## 概要

Huntressが観測したMicrosoft Azure CLIを標的とする大規模自動化パスワードスプレー攻撃。インターネットインフラ事業者LSHIY LLC（AS32167）管理下のIPv6アドレス範囲を発信源とし、2週間で8100万回超のログイン試行を実施、64組織で少なくとも78件のMicrosoftアカウントを侵害した。非推奨のOAuthフロー「ROPC（Resource Owner Password Credentials）」を悪用し、条件付きアクセスポリシー（CAP）によるMFA保護を回避する点が特徴。

**同一性の判断に役立つ情報：**
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

- [2026-07-05 Azure CLIを狙った8100万回超のパスワードスプレー攻撃、78アカウントが侵害](../articles/2026-07-05-azure-cli-password-spray-81million.md)
- [2026-07-03 Microsoft 365に8100万回超のパスワードスプレー攻撃、Azure CLIのROPCフローでMFAを回避](../articles/2026-07-03-microsoft-365-password-spray-ropc.md)
- [2026-07-01 Azure CLIを狙った大規模パスワードスプレー攻撃、8100万回超の試行で78アカウント侵害](../articles/2026-07-01-azure-cli-password-spray-lshiy.md)
