# Joomla iCagenda / Balbooa Forms 拡張機能 ゼロデイ RCE（2026年6-7月）

## 概要

Joomla 用イベント管理拡張機能「iCagenda」およびフォーム作成拡張機能「Balbooa Forms」に、いずれも CVSS 10.0 の最大深刻度を持つ任意ファイルアップロード脆弱性が存在し、CVE 採番前からゼロデイとして実際に悪用されていたことが判明した。CISA は2026年7月、両脆弱性を Known Exploited Vulnerabilities（KEV）カタログに追加し、連邦政府機関に対し2026年7月13日までの修正を義務付けた。

**同一性の判断に役立つ情報：**
- CVE-2026-48939: iCagenda 拡張機能 - ファイル添付機能経由の任意ファイルアップロードからPHPコード実行（CVSS 10.0）。mySites.guru によると2026年6月15日からゼロデイとして自動化攻撃で悪用。JoomliC が v4.0.8 / v3.9.15 で修正。
- CVE-2026-56291: Balbooa Forms 拡張機能 - 任意ファイルアップロードからRCE（CVSS 10.0）。2026年7月8日、mySites.guru の顧客への実攻撃で発見。v2.4.1 で修正。
- 対象CMS: Joomla（拡張機能経由）
- CISA KEV 追加・FCEB対応期限: 2026年7月13日

## タイムライン

- [2026-07-14 CISA、Joomla の iCagenda・Balbooa Forms 拡張機能のゼロデイ悪用をKEVカタログに追加](../articles/2026-07-14-joomla-icagenda-balbooa-zero-day.md)
