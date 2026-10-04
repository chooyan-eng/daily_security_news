# Dell Container Storage Modulesに複数の重大脆弱性（DSA-2026-448、ハードコード認証情報CVSS 10.0等）

- **日付**: 2026-10-04
- **出典**: [Dell DSA-2026-448 / CCB Belgium](https://ccb.belgium.be/advisories/warning-critical-information-disclosure-vulnerability-dell-container-storage-modules-can)
- **トピック**: [Dell Container Storage Modules DSA-2026-448 重大脆弱性（2026年10月）](../topics/dell-container-storage-modules-dsa-2026-448.md)
- **分類**: 新規

## 概要

DellはKubernetes向けストレージ機能Container Storage Modulesの重大な脆弱性を修正するセキュリティ更新DSA-2026-448を公開した。ハードコードされた認証情報（CVE-2026-40710、CVSS 10.0）とOSコマンドインジェクション（CVE-2026-40711）が含まれる。

## 詳細

- CVE-2026-40710: 公開ソースリポジトリ上にハードコードされた認証情報が含まれ、悪用されると認証セッションの侵害、キャッシュデータの持ち出し、他サービスへの横展開につながる（CVSS 10.0）。
- CVE-2026-40711: csi-powerstore / csi-unity / csi-powerflex / csi-powermax v2.16.0にOSコマンドインジェクションがあり、高権限のリモート攻撃者がコマンドを実行できる。
- 報道では未認証のリモート攻撃者が管理者権限を得られる可能性にも言及されている。実悪用は確認されていない。

対策: DSA-2026-448に従い修正版へ更新し、リポジトリ上で露出した認証情報をローテーションする。

注意: 一部の詳細は検索結果の要約に基づく。DSA-2026-448と各CVEの対応関係は公式アドバイザリで確認のこと。
