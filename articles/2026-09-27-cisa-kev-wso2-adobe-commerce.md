# CISA、WSO2とAdobe Commerce/Magentoの実悪用脆弱性2件をKEVカタログに追加

- **日付**: 2026-09-27
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/wso2-and-adobe-commerce-flaws-exploited.html), [BleepingComputer](https://www.bleepingcomputer.com/news/security/cisa-warns-of-sharepoint-wso2-adobe-commerce-flaws-exploited-in-attacks/), [Security Affairs](https://securityaffairs.com/199704/hacking/u-s-cisa-adds-adobe-and-wso2-flaws-to-its-known-exploited-vulnerabilities-catalog.html)
- **トピック**: [WSO2 API Manager CVE-2026-5430 JWT認証バイパス脆弱性（2026年9月）](../topics/wso2-api-manager-cve-2026-5430-jwt-bypass.md)
- **分類**: 続報

## 概要

米CISAは2026年9月24日、WSO2製品群のJWT認証バイパス脆弱性CVE-2026-5430と、Adobe Commerce/Magentoのアカウント乗っ取り脆弱性CVE-2026-71362を、実悪用が確認されたとしてKnown Exploited Vulnerabilities（KEV）カタログに追加した。連邦政府機関には9月27日までの対応が求められている。

## 詳細

CVE-2026-5430（CVSS 9.8）は、WSO2のAPI Control Plane、API Manager、Traffic Manager、Universal Gatewayに影響するパストラバーサル型の脆弱性で、任意ファイルアップロードからリモートコード実行につながる。watchTowrは、自社ハニーポットに対する実環境での悪用試行を2026年9月13日から観測していたと報告しており、9月16日の脆弱性公表からおよそ1週間強でCISAのKEV入りとなった。

CVE-2026-71362（CVSS 9.1）はAdobe Commerce/Magento Open Sourceの認可不備（Incorrect Authorization）で、認証済みセッションを別の顧客アカウントへ切り替えられることにより、ユーザー操作なしに任意の顧客アカウントを乗っ取れる。ECセキュリティベンダーSansecは、2026年8月11日のパッチ公開直後から自社WAF「Sansec Shield」で悪用試行を検知・ブロックしていたとすでに報告しており、今回のKEV追加はその実悪用状況を米当局が正式に確認した形となる。

CISAはFederal Civilian Executive Branch（FCEB）機関に対し、両脆弱性について2026年9月27日までにパッチ適用または緩和策の実施、あるいは該当製品の利用中止を求めている。いずれもAPIゲートウェイやECプラットフォームという、外部公開されたWebアプリケーション基盤の中核コンポーネントであり、パッチ未適用環境は依然として攻撃対象になり得るため、民間企業についても速やかな対応が推奨される。

本記事は、[WSO2 API Manager CVE-2026-5430 JWT認証バイパス脆弱性](../topics/wso2-api-manager-cve-2026-5430-jwt-bypass.md)と[Adobe Commerce / Magento CVE-2026-71362 アカウント乗っ取り脆弱性](../topics/adobe-commerce-cve-2026-71362.md)の両トピックの続報を兼ねる。
