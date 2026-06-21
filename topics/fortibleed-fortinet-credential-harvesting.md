# FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）

## 概要

SOCRadar が「FortiBleed」と命名した Fortinet FortiGate Firewall を標的とした大規模認証情報収集キャンペーン。世界194カ国の30,791台以上のデバイスが侵害され、銀行・通信・病院・政府機関・大学などが対象。その後の調査で犯罪グループが73,932台のFortiGateデバイスへのアクセスをダークウェブで販売し始めたことが判明。デフォルト認証情報の悪用と侵害済みデバイスを踏み台とした再帰的な認証情報収集が特徴。根本原因はCVE-2022-40684（パッチ済み）の遅延適用。

**同一性の判断に役立つ情報：**
- キャンペーン名: FortiBleed
- 対象製品: Fortinet FortiGate Firewall
- 初期侵害台数: 30,791台以上
- 最終的な販売対象: 73,932台（インターネット公開FortiGateの約半数）
- 影響国数: 194カ国
- 発見者: SOCRadar（初報）、Volodymyr "Bob" Diachenko（販売確認）
- 主要手法: デフォルト認証情報、パスワードリスト攻撃、トラフィック傍受
- 根本CVE: CVE-2022-40684（2022年10月パッチ済み）
SOCRadar が「FortiBleed」と命名した Fortinet FortiGate Firewall を標的とした大規模認証情報収集キャンペーン。最新分析では世界194カ国の73,932台（当初発表30,791台から倍増）のデバイスの認証情報が流出。銀行・通信・病院・政府機関・大学などが対象で、Oracle・Chevron・FedEx・Samsung 等の大手企業も含まれる。ロシア語話者のサイバー犯罪グループが過去の侵害ダンプとインフォスティーラーマルウェアのログを組み合わせた自動化攻撃を実施。

## タイムライン

- [2026-06-21 FortiBleed続報 — 侵害デバイス86,644台に拡大、CISA が緊急警告・デフォルトアカウント悪用が主因](../articles/2026-06-21-fortibleed-86k-cisa-warning.md)
- [2026-06-19 FortiBleed続報 - 犯罪グループが73,932台のFortiGateデバイスへのアクセスを販売開始](../articles/2026-06-19-fortibleed-75k-fortigate-credential-sale.md)
- [2026-06-18 FortiBleed 続報：侵害デバイス数が73,932台に拡大、規模が倍増と判明](../articles/2026-06-18-fortibleed-73k-devices-update.md)
- [2026-06-17 FortiBleed：30,000台以上のFortinet Firewallが世界194カ国で認証情報を流出](../articles/2026-06-17-fortibleed-30k-fortinet-firewalls.md)
