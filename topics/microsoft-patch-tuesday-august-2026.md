# Microsoft Patch Tuesday 2026年8月

## 概要

Microsoftが2026年8月11日に月例パッチを公開し、421件のCVEを修正。うちWindows Ancillary Function Driver for WinSock（afd.sys）の権限昇格ゼロデイ CVE-2026-68820 は北朝鮮系脅威アクター Lazarus による積極的悪用が確認されている。あわせて、SharePointのRCE脆弱性チェーンを構成する CVE-2026-63520 も修正された。

**同一性の判断に役立つ情報：**
- 修正件数: 421件のCVE（Critical 62件、悪用済みゼロデイ1件、公開済みゼロデイ3件）
- CVE-2026-68820: afd.sys（WinSockカーネルドライバ）のuse-after-free、Lazarusが2026年7月初旬から悪用しSYSTEM権限奪取・FudModuleルートキット/ForestTigerバックドア展開（Operation Dream Job）
- CVE-2026-63520: SharePointのBusiness Connectivity Servicesにおける安全でない.NET型インスタンス化によるRCE（CVSS 8.1）。認証バイパスCVE-2026-55040と連鎖させると未認証RCEに発展しうる。Rapid7とMicrosoftが共同開示。悪用は本稿執筆時点で未確認
- 対応: KB5121003（Windows 11）/ KB5120249（Windows 10）を早急に適用。CVE-2026-68820はCISA KEVに追加済み

## タイムライン

- [2026-08-13 Microsoft 2026年8月Patch Tuesday：Lazarus悪用のWinSockゼロデイとSharePoint RCEチェーンを修正](../articles/2026-08-13-microsoft-patch-tuesday-august-2026.md)
