# Adobe、ColdFusionとCampaign Classicで最大深刻度（CVSS 10.0）の脆弱性3件を修正

- **日付**: 2026-08-15
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/adobe-patches-three-cvss-100-coldfusion.html)
- **トピック**: [Adobe 2026年8月定例セキュリティ更新](../topics/adobe-patch-tuesday-august-2026.md)
- **分類**: 続報

## 概要

Adobeは2026年8月の定例セキュリティ更新の一環として、ColdFusionおよびCampaign Classicに存在する最大深刻度（CVSS 10.0）の脆弱性3件を修正した。同月の更新ではAdobe Commerceのアカウント乗っ取り脆弱性CVE-2026-71362も修正されており、複数の主要製品で重大な脆弱性が同時に公開された。

## 詳細

### 修正された脆弱性

Adobeは2026年8月の月例パッチで、ColdFusionとCampaign Classicに存在するCVSS 10.0（満点）の脆弱性3件を含む複数のセキュリティ更新を公開した。CVSS 10.0は攻撃元区分・攻撃条件の複雑さ・必要な権限・ユーザー関与のいずれについても攻撃者に最も有利な条件が揃っていることを示し、通常は「未認証・低複雑度でリモートから完全な侵害が可能」なケースに付与される。

### ColdFusion・Campaign Classicのリスク

ColdFusionはエンタープライズ向けのWebアプリケーションサーバーとして金融・製造・公共機関など幅広い業種で稼働しており、過去にも複数の重大なRCE脆弱性が実際に悪用された実績がある製品である。Campaign Classicはマーケティングオートメーション製品で、顧客の個人情報や配信データを扱う基幹システムとして運用されるケースが多い。

### 同月のAdobe Commerce脆弱性との関係

同じ2026年8月の定例更新でAdobe Commerce（Magento）のアカウント乗っ取り脆弱性 CVE-2026-71362（CVSS 9.1）も修正されており、こちらはパッチ公開直後からセキュリティ企業Sansecが実際の悪用試行を確認している。ColdFusion・Campaign Classicの脆弱性については本稿執筆時点で悪用の証拠は報告されていないが、CVSS 10.0という深刻度と、ColdFusionが過去に実際の攻撃で悪用されてきた実績を踏まえると、早期のパッチ適用が強く推奨される。

### 対策

- ColdFusion、Campaign Classicの運用者は2026年8月のセキュリティアドバイザリを確認し、該当パッチを速やかに適用する
- インターネットに公開されたColdFusion管理コンソールへのアクセス制限を再確認する
- Adobe Commerceを含め、同月にAdobe製品全般で重大な脆弱性が集中して公開されていることから、Adobe製品全体の資産棚卸しとパッチ適用状況の点検を行う
