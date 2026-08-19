# Adobe 2026年8月定例セキュリティ更新

## 概要

Adobeが2026年8月の定例セキュリティ更新（Patch Tuesday）で公開した、複数製品にまたがる重大脆弱性群。Adobe Commerce（Magento）ではセッション切り替えによるアカウント乗っ取りが可能な CVE-2026-71362（CVSS 9.1）が修正され、パッチ公開直後からセキュリティ企業Sansecが実際の悪用試行を検知・ブロックした（APSB26-92）。同時に、ColdFusionおよびCampaign Classicでも最大深刻度（CVSS 10.0）の脆弱性3件が修正されている。

**同一性の判断に役立つ情報：**
- 更新月: 2026年8月（Adobe定例パッチ）
- CVE-2026-71362（Adobe Commerce/Commerce B2B/Magento Open Source）: CVSS 9.1、不適切な認可、セッション切り替えによるアカウント乗っ取り、アドバイザリ番号 APSB26-92
- ColdFusion / Campaign Classic: CVSS 10.0の脆弱性3件
- 悪用状況: Adobe Commerce (CVE-2026-71362) はパッチ公開直後からSansecが悪用試行を検知。ColdFusion/Campaign Classicは本稿時点で悪用の証拠なし

## タイムライン

- [2026-08-15 Adobe、ColdFusionとCampaign Classicで最大深刻度（CVSS 10.0）の脆弱性3件を修正](../articles/2026-08-15-adobe-coldfusion-campaign-classic-cvss10.md)
- [2026-08-15 Adobe Commerce の重大脆弱性CVE-2026-71362、パッチ公開直後から悪用でアカウント乗っ取り](../articles/2026-08-15-adobe-commerce-cve-2026-71362-exploited.md)
