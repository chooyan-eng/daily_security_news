# Microsoft、ShinyHuntersによる1年間のSalesforce攻撃パスを3種類に整理・分析

- **日付**: 2026-07-14
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/07/13/defending-saas-based-applications-against-shinyhunters-oauth-abuse/)
- **分類**: 関連

## 概要

Microsoftは2026年7月13日、脅威アクターShinyHuntersがこの1年間に展開してきたSalesforce環境への攻撃を3種類の攻撃パスに整理したセキュリティブログを公開した。いずれもSalesforceそのものの脆弱性ではなく、OAuthトークンを利用した第三者SaaS連携の信頼関係を悪用する手口である点が共通しており、既報のKlue/Icarusキャンペーンとも手口が共通する。

## 詳細

### ブログの内容

Microsoft Security Blogは、ShinyHuntersが過去1年間にわたりSalesforce環境を標的として展開してきた攻撃手法を3つの攻撃パスに分類して解説した。いずれのケースも、Salesforce本体の脆弱性を突くものではなく、Salesforceと連携する第三者SaaSアプリケーションに発行されたOAuthトークンの窃取・悪用を起点としている点で共通する。

代表例として挙げられているのが、2026年6月8日〜18日にかけて発生したSalesloft Drift連携を経由するデータ窃取キャンペーン（脅威アクターUNC6395、通称「Icarus」）である。このケースでは、Salesloft DriftアプリケーションにSalesforceが発行していたOAuthトークンが侵害され、700以上の組織のSalesforceインスタンスからサポートケース内のテキスト、連絡先・アカウント情報に加え、AWSキーやSnowflakeトークン、VPN認証情報等の平文の認証情報が窃取された。検知は2026年6月19日で、DriftのOAuthトークンは即座に失効され、Salesforce AppExchangeからも削除された。

### Klue/Icarusキャンペーンとの関係

本ブログで扱われている攻撃手法は、当リポジトリで既に追跡している「Klue OAuth侵害と『Icarus』キャンペーン」（2026年6月）と、攻撃手法（第三者SaaS統合のOAuthトークン窃取によるSalesforceデータ窃取）およびSalesforceという標的の面で類似する。ただし本ブログが扱う中心事例（Salesloft Drift経由のUNC6395キャンペーン）は、Klueを侵害起点とする別のインシデントであり、同一事案と断定できるだけの情報はないため、直接の続報ではなく関連情報として扱う。

### 技術的補足

本件は、SaaSアプリケーション間のOAuth連携が持つ「暗黙の信頼」が攻撃の共通基盤となっている点を改めて示している。単一のSaaS統合ポイント（Klue、Salesloft Driftなど）の侵害が、そこに接続された多数の顧客組織のCRMデータへの一括アクセスにつながる構造は、SaaSエコシステム全体のセキュリティ設計における構造的リスクである。

---

## 関連記事

- [Klue OAuth侵害を起点とする「Icarus」キャンペーン - Salesforce CRMデータが多数企業から窃取](../articles/2026-06-19-klue-icarus-salesforce-oauth-breach.md) - 同種のOAuthトークン悪用によるSalesforce CRMデータ窃取手口
- [Klue OAuth侵害 続報：Icarus の被害組織リストが拡大](../articles/2026-06-23-klue-icarus-victim-list-grows.md) - 同じ脅威アクター「Icarus」による関連キャンペーン
