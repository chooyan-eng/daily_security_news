# FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）

## 概要

SOCRadar が「FortiBleed」と命名した Fortinet FortiGate Firewall を標的とした大規模認証情報収集キャンペーン。世界194カ国の86,644台（インターネット公開FortiGateの約50%）のデバイスの認証情報が流出。銀行・通信・病院・政府機関・大学などが対象で、Oracle・Chevron・FedEx・Samsung 等の大手企業も含まれる。ロシア語話者のサイバー犯罪グループが過去の侵害ダンプとインフォスティーラーマルウェアのログを組み合わせた自動化攻撃を実施。CISA が 2026年6月19日に公式アラートを発令し、即時の緩和措置適用を求めた。

**同一性の判断に役立つ情報：**
- キャンペーン名: FortiBleed
- 対象製品: Fortinet FortiGate Firewall
- 最新侵害台数: 86,644台（インターネット公開FortiGateの約50%）
- 影響国数: 194カ国
- 発見者: SOCRadar（初報）、Volodymyr "Bob" Diachenko（販売確認）
- 主要手法: デフォルト認証情報、パスワードリスト攻撃、トラフィック傍受
- 根本CVE: CVE-2022-40684（2022年10月パッチ済み）
- CISA アラート発令日: 2026年6月19日

## タイムライン

- [2026-06-23 FortiBleed 続報：攻撃者が3万件の「有効なFortinet ログイン」データベースを構築](../articles/2026-06-23-fortibleed-30k-working-logins.md)
- [2026-06-22 FortiBleed続報：CISAがFortinetユーザーに緊急対策を要請、侵害デバイス数86,644台に](../articles/2026-06-22-fortibleed-cisa-86k-warning.md)
- [2026-06-21 FortiBleed続報 — 侵害デバイス86,644台に拡大、CISA が緊急警告・デフォルトアカウント悪用が主因](../articles/2026-06-21-fortibleed-86k-cisa-warning.md)
- [2026-06-20 FortiBleed続報 - CISA警告発令、侵害デバイスが86,644台に増加](../articles/2026-06-20-fortibleed-86644-cisa-warning.md)
- [2026-06-19 FortiBleed続報 - 犯罪グループが73,932台のFortiGateデバイスへのアクセスを販売開始](../articles/2026-06-19-fortibleed-75k-fortigate-credential-sale.md)
- [2026-06-18 FortiBleed 続報：侵害デバイス数が73,932台に拡大、規模が倍増と判明](../articles/2026-06-18-fortibleed-73k-devices-update.md)
- [2026-06-17 FortiBleed：30,000台以上のFortinet Firewallが世界194カ国で認証情報を流出](../articles/2026-06-17-fortibleed-30k-fortinet-firewalls.md)
