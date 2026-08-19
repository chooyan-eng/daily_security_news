# ShinyHunters、仏Questel SASを標的に – Salesforceから2,100万件超のレコードを窃取したと主張

- **日付**: 2026-08-07
- **出典**: [DeXpose](https://www.dexpose.io/shinyhunters-breach-questel-sas-french-ip-giant-under-siege/) / [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/07/13/defending-saas-based-applications-against-shinyhunters-oauth-abuse/)
- **トピック**: [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md)
- **分類**: 新規

## 概要

データ恐喝グループShinyHuntersは2026年8月2日、フランスの知的財産サービス大手Questel SASを被害者としてリークサイトに公表した。同社のSalesforce環境から2,100万件超のPIIを含むレコードと147GB超の内部データを窃取したと主張し、8月4日を最終期限として身代金を要求している。暗号化被害を示す証拠はなく、データ窃取のみによる二重恐喝型の攻撃とみられる。

## 詳細

### 概要

ShinyHuntersは2026年8月2日、フランスの知的財産（IP）管理サービス大手Questel SASを標的とした攻撃をリークサイト上で公表した。同グループはQuestelのSalesforce環境から2,100万件を超えるレコード（顧客・従業員のPIIを含む）と、147GB超の内部企業データを窃取したと主張している。8月4日を最終期限とし、これを過ぎればデータを公開すると警告した。

### 手口

本件の具体的な初期侵入経路は個別には明らかにされていないが、Microsoftは2026年7月、ShinyHuntersと重複する手口を持つ脅威アクターが、ボイスフィッシング（ビッシング）やサプライチェーン侵害を通じてSalesforceなどの顧客SaaSアプリケーションを狙い、信頼されたOAuth連携を悪用して不正アクセス・データ持ち出し・永続化を行っていると報告している。この手口は2026年6月に確認されたKlue発のOAuthトークン窃取キャンペーン「Icarus」とは別の攻撃者・キャンペーンだが、SaaS連携（特にSalesforce OAuth）を突く同様のパターンが継続していることを示している。

### 恐喝の形態

暗号化されたファイルやランサムノート、マルウェア検体の存在は報告されておらず、データ窃取と公開の脅迫による二重恐喝（データ恐喝）型の攻撃であることが強調されている。

### 対策

1. SalesforceなどSaaSアプリケーションに接続された第三者OAuthアプリ・トークンの棚卸しと不要な連携の削除
2. 異常なAPIコール・大量データエクスポートの監視
3. ボイスフィッシング対策としてのヘルプデスク本人確認プロセスの強化
4. Salesforce Shield等によるイベント監視・DLP設定の見直し

---

## 関連記事

なし（新規トピック）
