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

## タイムライン

- [2026-07-05 Azure CLIを狙った8100万回超のパスワードスプレー攻撃、78アカウントが侵害](../articles/2026-07-05-azure-cli-password-spray-81million.md)
