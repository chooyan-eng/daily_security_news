# OpenAI「Poisoned Tenant」フィッシングキャンペーン（2026年）

## 概要

Push Securityが発見した「Poisoned Tenant」キャンペーンでは、攻撃者がGmailアドレスで正規企業を騙るOpenAI（ChatGPT）テナントを作成し、標的企業の従業員に招待メールを送る。招待メールはOpenAIの正規インフラ（noreply@tm.openai.com）から送信されるため、SPF・DKIM・DMARCをすべて通過する。従業員がそのChatGPTワークスペースを業務利用すると、ソースコード・内部文書・顧客データ等のプロンプト内容が攻撃者のテナントに記録される。

**同一性の判断に役立つ情報：**
- キャンペーン名: Poisoned Tenant
- 発見者: Push Security
- 攻撃手法: OpenAI APIを悪用したフィッシング用テナント作成 → 企業従業員への正規招待メール送信 → 業務情報収集
- 送信元: noreply@tm.openai.com（正規OpenAIインフラ）
- ターゲット: セキュリティ企業を含む複数の企業・組織
- 狙い: AI プラットフォームへの業務プロンプト（ソースコード・機密文書・認証情報等）の窃取

## タイムライン

- [2026-06-27 「Poisoned Tenant」キャンペーン：攻撃者が企業を騙るOpenAIテナントを作成し従業員の機密情報を収集](../articles/2026-06-27-openai-poisoned-tenant-phishing-campaign.md)
