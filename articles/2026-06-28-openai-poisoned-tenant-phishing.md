# OpenAI「Poisoned Tenant」攻撃：偽組織招待で企業従業員を狙うフィッシングキャンペーン

- **日付**: 2026-06-27
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/cybersecurity-firms-targeted-by-fraudulent-openai-organization-invites/) / [TechRadar](https://www.techradar.com/pro/security/beware-hackers-have-hijacked-openais-invite-your-team-feature-to-break-into-your-business)
- **トピック**: [OpenAI「Poisoned Tenant」フィッシングキャンペーン（2026年）](../topics/openai-poisoned-tenant-phishing-2026.md)
- **分類**: 新規

## 概要

Push Security が発見した「Poisoned Tenant」と呼ばれる新型フィッシングキャンペーンで、攻撃者が正規の OpenAI 組織（テナント）機能を悪用し、企業名を騙った偽 ChatGPT ワークスペースに従業員を招待する攻撃が確認されている。招待メールは OpenAI の正規インフラから送信されるため、メールセキュリティフィルターをほぼすべてすり抜ける。

## 詳細

### 攻撃の仕組み

1. **偽テナント作成**: 攻撃者が Gmail アドレスを使って標的企業名（例：「Push Security Inc.」）を騙る OpenAI 組織を作成
2. **正規招待の送信**: OpenAI の公式通知アドレス（noreply@tm.openai.com）から招待メールが届く。メール認証チェック（DKIM/SPF）を通過し見た目は本物と変わらない
3. **権限付与**: 招待を承認すると標的は偽テナントの「Owner」権限を持つメンバーに追加される
4. **情報収集**: 攻撃者が CEO を装い偽のコミュニケーションを行い、企業の機密情報を ChatGPT プロジェクトやチャットに入力させる

### 発見の経緯

Push Security が複数の従業員に「Push Security Inc.」という組織名の OpenAI 招待が届いていることを発見。調査したところ、招待は本物の OpenAI サーバーから送信されており、テナントは攻撃者が Gmail アドレスで作成したことが判明。他の顧客も同様の攻撃を受けており、標的はサイバーセキュリティおよびテクノロジー分野の企業に集中している。

### 標的を特定した精度

攻撃者は各従業員の仕事用メールアドレスで招待しており、事前に標的調査（OSINT）を実施していることが示唆される。ランダムな大量配信ではなく、特定組織・特定人物を狙った標的型攻撃。

### 従来のフィッシングとの差異

| 従来型フィッシング | Poisoned Tenant |
|---|---|
| 偽のメール送信元 | OpenAI 公式インフラから送信 |
| メール認証で検出可能 | DKIM/SPF/DMARC を通過 |
| 偽サイトへの誘導 | 正規 ChatGPT サイトに誘導 |
| URL やドメイン詐称 | 詐称なし |

### 推奨される対策

- 予期しない SaaS 組織への招待は受け入れ前に帯域外で確認する
- OpenAI 等の SaaS テナントメンバーシップを定期監視する
- エンドユーザー向けセキュリティトレーニングで SaaS テナント招待のリスクを教育する
- ChatGPT for Work 等の AI ツールで入力する情報の機密区分ポリシーを策定する
