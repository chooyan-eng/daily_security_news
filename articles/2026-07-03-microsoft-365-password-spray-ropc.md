# Microsoft 365に8100万回超のパスワードスプレー攻撃、Azure CLIのROPCフローでMFAを回避

- **日付**: 2026-07-03
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-365-accounts-with-81-million-login-attempts/)（Huntress調査）
- **トピック**: [Microsoft 365 ROPCパスワードスプレーキャンペーン（2026年）](../topics/microsoft-365-password-spray-ropc-2026.md)
- **分類**: 新規

## 概要

2026年6月12日から26日にかけて、Microsoft 365テナントを標的とした大規模なパスワードスプレー攻撃が観測された。攻撃者はAzure CLI経由のOAuth ROPC（Resource Owner Password Credentials）認証フローを悪用し、条件付きアクセスポリシーの設定不備を突いてMFAを回避。8100万回超のログイン試行の末、64組織にまたがる78アカウントの侵害に成功した。

## 詳細

### キャンペーンの概要

セキュリティ企業Huntressの報告によると、2026年6月12日から26日にかけて、身元不明の脅威アクターがMicrosoft 365アカウントに対する大規模なパスワードスプレー攻撃を実施した。攻撃トラフィックはLSHIY LLCが保有するIPv6アドレス範囲（AS32167）から発信されたことが確認されている。

攻撃の規模は8100万回を超えるログイン試行に達し、最終的に64組織にまたがる78アカウントの認証情報突破に成功したことが確認された。

### 技術的手法：ROPCフローの悪用

本キャンペーンの特徴は、Azure CLIを介したOAuthの「Resource Owner Password Credentials（ROPC）」フローを悪用した点にある。ROPCフローは本来、ユーザー名とパスワードを直接用いてトークンを取得する認証方式だが、これが多要素認証（MFA）を回避する経路として悪用された。

具体的には、条件付きアクセスポリシー（Conditional Access Policy）がMFA適用範囲を特定のアプリケーションやグループのみに限定していたり、レポート専用モード（report-only mode）のまま本番運用されていたりする設定不備がある環境において、Azure CLIを経由したROPC認証がMFAチェックをすり抜けてしまう。

### 対策への示唆

Microsoftは近年、レガシー認証プロトコルやROPCフローの段階的な廃止を進めているが、依然として有効な設定が残る環境が攻撃対象となっている。組織としては、条件付きアクセスポリシーがすべてのユーザー・アプリケーションに一貫して適用されているかを確認し、ROPCなどのレガシー認証フローを無効化することが強く推奨される。また、report-onlyモードで放置されているポリシーがないか棚卸しを行うことも重要な対策となる。

---

## 関連記事

なし
