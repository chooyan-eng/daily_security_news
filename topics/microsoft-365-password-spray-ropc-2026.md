# Microsoft 365 ROPCパスワードスプレーキャンペーン（2026年）

## 概要

2026年6月12日〜26日にかけて観測された、Microsoft 365テナントを標的とした大規模パスワードスプレー攻撃。攻撃者はAzure CLI経由のOAuth ROPC（Resource Owner Password Credentials）フローを悪用し、条件付きアクセスポリシーの設定不備を突いてMFAを回避。8100万回超のログイン試行の末、64組織・78アカウントの侵害に成功した。報告元はHuntress。

**同一性の判断に役立つ情報：**
- キャンペーン期間: 2026年6月12日〜26日
- 攻撃手法: Azure CLI経由のOAuth ROPCフロー悪用、MFA回避
- 攻撃規模: 8100万回超のログイン試行
- 侵害結果: 64組織・78アカウント
- 攻撃元: LSHIY LLC保有のIPv6アドレス範囲（AS32167）
- 報告元: Huntress

## タイムライン

- [2026-07-03 Microsoft 365に8100万回超のパスワードスプレー攻撃、Azure CLIのROPCフローでMFAを回避](../articles/2026-07-03-microsoft-365-password-spray-ropc.md)
