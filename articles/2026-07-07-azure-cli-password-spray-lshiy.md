# Microsoft 365 標的に8,100万回超のパスワードスプレー攻撃、Azure CLI経由でMFAを回避

- **日付**: 2026-07-07
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-365-accounts-with-81-million-login-attempts/), [The Hacker News](https://thehackernews.com/2026/07/azure-cli-password-spray-hits-at-least.html), [TechRadar](https://www.techradar.com/pro/security/81-million-login-attempts-hit-microsoft-365-accounts-as-hackers-try-password-spraying-to-force-entry-using-stolen-credentials-and-oauth-to-bypass-authentication)
- **トピック**: [Azure CLI パスワードスプレーキャンペーン「LSHIY」（2026年）](../topics/azure-cli-password-spray-lshiy-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業HuntressがMicrosoft 365環境を標的とした大規模パスワードスプレー攻撃を確認。2週間で8,100万回超のログイン試行が行われ、64組織にわたり78件のMicrosoft 365アカウントが侵害された。攻撃者はAzure CLI経由のROPC OAuth認証を悪用し、条件付きアクセスの設定不備によりMFAを回避した。

## 詳細

セキュリティ企業Huntressは、2026年6月12日から26日にかけて自社顧客環境を対象に、Microsoft 365アカウントを狙った攻撃的なパスワードスプレーキャンペーンを観測したと報告した。2週間の観測期間中に8,100万回を超えるログイン試行が記録され、最終的に64組織にまたがる78件のMicrosoft 365アカウントが侵害されたことが確認されている。

攻撃者は、過去のデータ侵害で漏洩し今なお有効なユーザー名・パスワードの組み合わせを用いて、Microsoft Azureのコマンドラインインターフェース（CLI）経由での認証を試みた。有効な認証情報の組み合わせが見つかると、攻撃者はROPC（Resource Owner Password Credentials）と呼ばれるOAuth認証方式を用いて認証を行った。ROPCはユーザー名とパスワードを直接用いてトークンを取得する古い認証フローであり、条件付きアクセス（Conditional Access）ポリシーの設定が不十分な環境では、多要素認証（MFA）を回避してしまうケースがある。

キャンペーンの規模は当初小さく、1日あたり2〜4件程度のアカウント侵害で推移していたが、2026年6月22日には23組織にまたがる30件のユーザーIDが一日で侵害されるという明確なエスカレーションが発生した。Huntressの分析では、パスワードスプレー攻撃全体が155倍以上に急増しており、組織あたり平均で月間1,964件のログイン失敗が記録されているという。

攻撃の帰属については明確になっていないが、Huntressは活動の発信元がLSHIY LLC（AS32167）が保有するIPv6アドレス範囲であったと指摘しており、このことからキャンペーンは「LSHIY」という名称で呼ばれている。

この攻撃が成功した背景には、MFAの設定不備が大きく関わっている。具体的には、（1）MFAが全てのクラウドアプリではなく特定のアプリケーションにのみ適用されていた、（2)特定のユーザーグループにのみMFAが強制されていた、（3）ポリシーが実際には強制されない「レポートのみ」モードで設定されていた、といった不備が確認された組織で被害が発生している。組織においては、条件付きアクセスポリシーをすべてのクラウドアプリケーション・全ユーザーに対して強制モードで適用すること、レガシー認証プロトコル（ROPCを含む）を無効化すること、Azure CLIからの認証ログを監視することが強く推奨される。
