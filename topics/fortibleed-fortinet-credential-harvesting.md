# FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）

## 概要

SOCRadar が「FortiBleed」と命名した Fortinet FortiGate Firewall を標的とした大規模認証情報収集キャンペーン。最新分析では世界194カ国の73,932台（当初発表30,791台から倍増）のデバイスの認証情報が流出。銀行・通信・病院・政府機関・大学などが対象で、Oracle・Chevron・FedEx・Samsung 等の大手企業も含まれる。ロシア語話者のサイバー犯罪グループが過去の侵害ダンプとインフォスティーラーマルウェアのログを組み合わせた自動化攻撃を実施。

**同一性の判断に役立つ情報：**
- キャンペーン名: FortiBleed
- 対象製品: Fortinet FortiGate Firewall / SSL VPN
- 侵害台数: 73,932台（2026-06-18 最新分析）
- 影響国数: 194カ国
- 影響ドメイン数: 21,000以上
- 発見者: SOCRadar（当初）、Volodymyr "Bob" Diachenko（詳細データ発見）
- 主要手法: 過去の侵害ダンプ＋インフォスティーラーログによる認証情報収集、約11.6億回の認証試行
- 主要被害国: インド、米国（全体の約1/3）

## タイムライン

- [2026-06-18 FortiBleed 続報：侵害デバイス数が73,932台に拡大、規模が倍増と判明](../articles/2026-06-18-fortibleed-73k-devices-update.md)
- [2026-06-17 FortiBleed：30,000台以上のFortinet Firewallが世界194カ国で認証情報を流出](../articles/2026-06-17-fortibleed-30k-fortinet-firewalls.md)
