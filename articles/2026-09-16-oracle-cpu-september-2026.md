# Oracle、2026年9月定例パッチで673件の脆弱性を修正、実質800件超の過去最大級リリース

- **日付**: 2026-09-16
- **出典**: [Oracle Critical Patch Update Advisory - September 2026](https://www.oracle.com/security-alerts/cspusep2026.html), [SecurityWeek](https://www.securityweek.com/oracle-patches-800-vulnerabilities-in-september-2026-security-update/)
- **トピック**: [Oracle Critical Patch Update 2026年9月](../topics/oracle-cpu-september-2026.md)
- **分類**: 新規

## 概要

Oracleは2026年9月15日、四半期定例セキュリティパッチ「Critical Patch Update（CPU）」を公開した。673件の脆弱性修正を含み、他の修正に同梱される形で解消された130件超を合わせると実質800件超に及ぶ、過去最大級の規模のリリースとなった。17製品ファミリーにまたがり、Critical格付けが104件、認証不要でリモートから悪用可能なものが240件超含まれる。

## 詳細

今回のCPUでは673件のセキュリティ修正が公式に公開されたが、Oracleはこれとは別に、他の不具合修正に同梱される形で静かに解消された脆弱性が130件超あるとしており、単一リリースで修正された脆弱性の実質的な合計は800件を超える。

深刻度の内訳は、Critical（緊急）が104件（全体の15.5%）、Important（重要）が503件（74.7%）、Medium（中）が59件となっている。対象は17の製品ファミリーにまたがり、100件超がCVSS基準でCritical格付け、240件超が認証不要でリモートから悪用可能とされている。

製品別では、Oracle E-Business Suiteが159件と最多で全体の約24%を占め、Oracle Fusion Middlewareが153件（うちCritical格付け67件）と続く。E-Business SuiteおよびFusion Middlewareはいずれも企業の基幹業務システムやWebアプリケーション基盤として広く利用されており、既に過去にはE-Business Suiteの脆弱性が実環境で悪用され侵害に至った事例も報告されている。

Oracle製品は業務システムの中核として長期間稼働し続けるケースが多く、パッチ適用が後回しにされがちである一方、認証不要でリモート悪用可能な脆弱性が多数含まれる今回のリリースは、影響を受ける組織にとって速やかな対応が求められる内容となっている。

---
