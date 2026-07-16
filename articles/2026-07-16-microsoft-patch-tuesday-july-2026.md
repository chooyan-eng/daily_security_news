# Microsoft Patch Tuesday 2026年7月：過去最多622件を修正、ゼロデイ3件を含む

- **日付**: 2026-07-16
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-july-2026-patch-tuesday-fixes-massive-570-flaws-3-zero-days/), [Malwarebytes](https://www.malwarebytes.com/blog/bugs/2026/07/july-2026-patch-tuesday-fixes-622-microsoft-cves-including-three-zero-days), [Tenable](https://www.tenable.com/blog/microsofts-july-2026-patch-tuesday-addresses-569-cves-cve-2026-56155-cve-2026-56164)
- **トピック**: [Microsoft Patch Tuesday 2026年7月](../topics/microsoft-patch-tuesday-july-2026.md)
- **分類**: 新規

## 概要

Microsoftが2026年7月14日に月例セキュリティ更新プログラムをリリース。単月として過去最多となる622件（CVEベース）の脆弱性を修正し、うち59件がCritical。実際に悪用されたゼロデイ2件と、公開済みゼロデイ1件が含まれる。

## 詳細

積極的に悪用が確認された2件のゼロデイは以下の通り。

- **CVE-2026-56155**：Active Directory Federation Services（AD FS）の特権昇格脆弱性。悪用に成功すると管理者権限を取得できる。Microsoftのインシデント対応部門であるDART（Detection and Response Team）が実際の攻撃調査の過程で発見・報告したとクレジットされており、既に実環境での攻撃に利用されていたことを示唆する。
- **CVE-2026-56164**：Microsoft SharePoint Serverの特権昇格脆弱性。重要な機能に対する認証欠如の不備により、未認証のリモート攻撃者がユーザー操作なし・低い攻撃複雑度でネットワーク経由の特権昇格を行える。悪用の詳細な手口は本記事執筆時点で公開されていない。

このほか、公開されているが実際の悪用は未確認のゼロデイとして、Windows BitLockerのセキュリティ機能バイパス脆弱性CVE-2026-50661が挙げられる。悪用されると暗号化されたデータへのアクセスを許す可能性がある。

Critical評価の59件のうち48件がリモートコード実行（RCE）、9件が特権昇格、1件がセキュリティ機能バイパス、1件がなりすましに分類される。修正件数・Critical件数ともに過去の月例更新を上回る規模となっており、企業のパッチ適用・トリアージ作業への負荷増大が指摘されている。

なお、SharePoint関連の脆弱性が今月分にも含まれている点は、同製品を標的とした攻撃キャンペーンが継続的に発生している状況（Storm-2603によるオンプレミスSharePoint悪用など）と合わせて注視が必要である。
