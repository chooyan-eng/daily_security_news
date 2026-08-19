# VMware vCenter/ESX 重大脆弱性 VMSA-2026-0006（2026年）

## 概要

BroadcomがVMware Security Advisory VMSA-2026-0006にて修正した、vCenter Server／ESXiに影響する5件の脆弱性群。うち3件が重大（Critical）：認証バイパス（CVE-2026-59309）、リモートコード実行（CVE-2026-59310、CVSS 9.8）、VMXNET3経由のVMエスケープ（CVE-2026-47876、CVSS 9.3）。2026年7月29日公開。

**同一性の判断に役立つ情報：**
- アドバイザリ: VMSA-2026-0006（2026年7月29日）
- CVE-2026-59309: VMware Directory Service 認証バイパス
- CVE-2026-59310: vCenter Server RCE（CVSS 9.8）
- CVE-2026-47876: VMXNET3経由のVMエスケープ（CVSS 9.3）
- 修正版: vCenter 9.1.0.0300 / 9.0.2.0100 / 8.0 U3k、ESXi 9.1.0.0200 / 9.0.2.0100 / 8.0 U3k
- CVE: CVE-2026-59309（関連: CVE-2026-59310）
- CVSS: 9.8（Critical）
- 対象製品: VMware vCenter Server、VMware Cloud Foundation / vSphere Foundation
- 勧告: VMSA-2026-0006（2026-07-29公開）
- 修正版: VMware vCenter Server 8.0 U3k、Cloud Foundation/vSphere Foundation 9.1.0.0300、9.0.2.0100
- 回避策: なし

## タイムライン

- [2026-07-30 VMware vCenterに認証バイパス等の重大脆弱性3件（CVE-2026-59309/59310ほか）、ブロードコムが修正](../articles/2026-07-30-vmware-vcenter-cve-2026-59309.md)
- [2026-07-29 Broadcom、VMware vCenter/ESXの重大脆弱性3件を含む計5件を修正（認証バイパス・VMエスケープ）](../articles/2026-08-02-vmware-vcenter-esx-critical-vulnerabilities.md)
