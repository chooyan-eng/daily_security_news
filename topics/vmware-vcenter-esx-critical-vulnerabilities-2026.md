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
- CVE: CVE-2026-59309（認証バイパス、vmdir）、CVE-2026-59310（ディレクトリトラバーサル、Syslog Server、RCE可能性）
- CVSS: いずれも9.8（Critical）
- アドバイザリ: VMSA-2026-0006（2026年7月29日公開）
- 修正バージョン: vCenter Server 8.0 U3k、VCF/vSphere Foundation 9.1.0.0300、9.0.2.0100
- CVE番号: CVE-2026-59310（CVSS 9.8、Critical）
- 脆弱性種別: ディレクトリトラバーサル（vCenter Syslogサーバー）→ システム権限でのRCE
- アドバイザリ公開: VMSA-2026-0006（2026年7月29日、Broadcom）
- 悪用開始確認: 2026年8月3日（QUIRSOがC2通信を検知）
- 悪用規模: 361台の被害IPアドレスを47カ国で観測、うち343台（約95%）が既に侵害済み（2026年8月5日時点）
- 永続化手法: 悪意あるcronジョブ設置＋reverse_sshによるC2接続
- 緩和策: 暫定回避策なし。即時パッチ適用が必須とBroadcomが表明

## タイムライン

- [2026-08-13 VMware vCenter脆弱性CVE-2026-59310、47カ国で積極的悪用を確認——リバースSSHで永続化](../articles/2026-08-13-vmware-vcenter-cve-2026-59310-exploited.md)
- [2026-08-03 VMware vCenter Serverに認証バイパス・RCEの重大脆弱性2件（CVE-2026-59309/CVE-2026-59310、CVSS 9.8）](../articles/2026-08-03-vmware-vcenter-auth-bypass-rce.md)
- [2026-07-30 VMware vCenterに認証バイパス等の重大脆弱性3件（CVE-2026-59309/59310ほか）、ブロードコムが修正](../articles/2026-07-30-vmware-vcenter-cve-2026-59309.md)
- [2026-07-29 Broadcom、VMware vCenter/ESXの重大脆弱性3件を含む計5件を修正（認証バイパス・VMエスケープ）](../articles/2026-08-02-vmware-vcenter-esx-critical-vulnerabilities.md)
