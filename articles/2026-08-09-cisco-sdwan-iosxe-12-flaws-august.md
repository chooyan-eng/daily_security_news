# Cisco、Catalyst SD-WANとIOS XEの12件の脆弱性を修正 — うち3件はCVSS 9.9

- **日付**: 2026-08-05
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/cisco-patches-12-sd-wan-and-ios-xe.html)
- **トピック**: [Cisco Catalyst SD-WAN CVE-2026-20262 ゼロデイ悪用（2026年6月）](../topics/cisco-sdwan-cve-2026-20262.md)
- **分類**: 関連

## 概要

Cisco は2026年8月5日、Catalyst SD-WAN SoftwareとIOS XE Softwareに存在する12件の脆弱性に対するセキュリティアドバイザリを一括公開した。うちCatalyst SD-WAN関連の3件（CVE-2026-20303、CVE-2026-20304、CVE-2026-20310）はCVSSスコア9.9の最高水準の深刻度で、IOS XEのコマンドインジェクション（CVE-2026-20272、CVSS 9.8）なども含まれる。現時点で積極的な悪用の報告はないが、同社製品はこれまでも複数のゼロデイ悪用を受けてきており、早急なパッチ適用が推奨される。

## 詳細

### 修正された主な脆弱性

**Catalyst SD-WAN Software（CVSS 9.9、3件）**
- CVE-2026-20303: 不適切な入力検証
- CVE-2026-20304: 不適切なアクセス制御
- CVE-2026-20310: ファイルアクセス前のリンク解決の不備

このほか、CVE-2026-20312（機密情報の平文保存）、CVE-2026-20313（指定数量の入力検証不備）も修正された。

**IOS XE Software**
- CVE-2026-20272（CVSS 9.8）: コマンドインジェクション
- CVE-2026-20267（CVSS 9.0）: 不適切なアクセス制御

Catalyst SD-WANの脆弱性は、デバイスの設定内容にかかわらず影響を受ける。IOS XEの脆弱性は、autonomousモードまたはcontrollerモードで動作している場合に影響する。

### 対応バージョン

Catalyst SD-WANは 20.9.10、20.12.8.1、20.15.6、20.18.4、26.1.2 で修正済み。IOS XEは 17.9.10、17.12.8、17.15.6、17.18.4／17.18.4a、26.1.2 で修正済み。ワークアラウンドは提供されていないため、該当バージョンへのアップグレードが必須となる。

### 既存トピックとの関連

Cisco Catalyst SD-WAN Managerを巡っては、2026年6月に発覚したパストラバーサル型ゼロデイ CVE-2026-20262（実際の悪用が確認されCISA KEVに追加）や、その後の第7のゼロデイ CVE-2026-20245 など、同一製品ラインで断続的に重大な脆弱性が発覚し悪用されてきた経緯がある。今回の12件は異なるCVE番号の新規脆弱性ではあるが、同じCatalyst SD-WAN製品ファミリーにおける脆弱性の集中的な発覚が続いている点で、一連の流れとして注視する価値がある。

---

## 関連記事

- [Cisco Catalyst SD-WAN Manager CVE-2026-20262 がゼロデイ悪用確認・CISA KEV追加](../articles/2026-06-17-cisco-sdwan-cve-2026-20262-zero-day.md) - 同一製品ラインで6月に発覚したゼロデイ脆弱性
- [Cisco Catalyst SD-WAN CVE-2026-20245 – Mandiant が「公開2ヶ月前からゼロデイ悪用」を確認](../articles/2026-06-25-cisco-sdwan-cve-2026-20245-mandiant.md) - 同一製品ラインの第7のゼロデイに関する続報
