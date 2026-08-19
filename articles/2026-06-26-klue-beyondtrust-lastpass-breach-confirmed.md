# Klue 侵害続報：BeyondTrust・LastPass など大手セキュリティ企業の被害が確認

- **日付**: 2026-06-26
- **出典**: [SecurityWeek](https://www.securityweek.com/beyondtrust-lastpass-impacted-by-klue-salesforce-incident/)
- **トピック**: [Klue OAuth侵害と「Icarus」キャンペーン（2026年6月）](../topics/klue-icarus-salesforce-oauth-2026.md)
- **分類**: 続報

## 概要

Klue 経由の Icarus キャンペーンによる Salesforce データ窃取の被害が広がりを見せ、BeyondTrust・LastPass を含む大手セキュリティ企業が被害を確認した。約24社のKlue顧客が自社の Salesforce インスタンスへの侵害を認め、「ハッカーがハッキングされた（Hackers Got Hacked）」とも揶揄される状況で、セキュリティベンダー自身の CRM データが流出した。

## 詳細

**新たに確認された被害企業**

BeyondTrust（特権アクセス管理）と LastPass（パスワード管理）が、Klue の OAuth トークン侵害を経由した Salesforce インスタンスへの不正アクセス被害を公式に確認した。これまでに判明している被害組織の一部：
- Huntress（セキュリティ運用企業）
- Recorded Future（脅威インテリジェンス）
- Tanium（エンドポイントセキュリティ）
- Jamf（Apple デバイス管理）
- Sprout Social・Gong・Insurity
- **BeyondTrust**（特権アクセス管理）
- **LastPass**（パスワードマネージャー）

**流出データの内容**

侵害された Salesforce インスタンスから以下のデータが流出した可能性：
- 企業名・製品情報・サブスクリプション詳細（使用数量・価格）
- ビジネス連絡先情報（氏名・メールアドレス・役職・電話番号・住所）
- マーケティング・セールスコミュニケーション
- 商談ノート・CRM レコード

**Salesforce の対応**

Salesforce は全顧客環境での Klue Battlecards アプリの接続を無効化した。Klue は 2026年6月12日に異常を検出し、6月13日に OAuth 認証情報を無効化してインテグレーションを停止、顧客に通知した。

**攻撃の経緯**

Icarus グループは Klue のバックエンドへの侵害後、OAuth トークンを収集する悪意あるコードを展開した。Klue のシステムからスタルトした形跡として、未使用だが有効なままのプロトタイプ用認証情報が悪用された可能性が指摘されている。

**セキュリティ企業が被害を受けた意義**

セキュリティ専門企業（BeyondTrust・Huntress・Recorded Future 等）がサプライチェーン経由で顧客 CRM データを流出させた今回の事案は、セキュリティツールベンダー自身もサプライチェーンリスクの対象であることを示している。OAuth 統合の不要なトークンのローテーション・無効化や、第三者連携の定期的な監査の重要性が改めて浮き彫りになった。
