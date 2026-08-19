# VMware vCenter Serverに認証バイパス・RCEの重大脆弱性2件（CVE-2026-59309/CVE-2026-59310、CVSS 9.8）

- **日付**: 2026-08-03
- **出典**: [Rapid7 Blog](https://www.rapid7.com/blog/post/etr-critical-vmware-vcenter-vulnerabilities-allow-authentication-bypass-and-remote-code-execution-cve-2026-59309-cve-2026-59310/)
- **トピック**: [VMware vCenter/ESX 重大脆弱性 VMSA-2026-0006（2026年）](../topics/vmware-vcenter-esx-critical-vulnerabilities-2026.md)
- **分類**: 続報
## 概要

Broadcomは7月29日、VMware vCenter Serverに存在する2件の重大な脆弱性（CVE-2026-59309、CVE-2026-59310、いずれもCVSS 9.8）を修正するセキュリティアドバイザリ「VMSA-2026-0006」を公開した。いずれも未認証のネットワーク攻撃者が悪用可能で、認証バイパスと任意コード実行につながる。仮想化基盤の管理コンソールという性質上、悪用された場合の影響は極めて大きい。

## 詳細

### 脆弱性の技術的詳細

**CVE-2026-59309**: VMware Directory Service（vmdir）コンポーネントに存在する重大な認証バイパス脆弱性。ネットワークアクセスを持つ未認証の攻撃者が認証機構を回避できる。

**CVE-2026-59310**: vCenter Syslog Serverコンポーネントに存在するディレクトリトラバーサル脆弱性。任意コード実行につながる可能性がある。

両脆弱性ともCVSSv3.1基本値は9.8（Critical）であり、ネットワーク経由・低攻撃難易度・認証不要という悪用条件の緩さが特徴。

### 影響を受ける製品・バージョン

- VMware vCenter Server 8.0（U3kより前）
- VMware Cloud Foundation / vSphere Foundation 9.1.0.0300より前
- VMware Cloud Foundation / vSphere Foundation 9.0.2.0100より前

### 修正状況

Broadcomは以下のバージョンで修正を提供している。

- VMware vCenter Server 8.0 Update 3k
- VMware Cloud Foundation / vSphere Foundation 9.1.0.0300
- VMware Cloud Foundation / vSphere Foundation 9.0.2.0100

### リスクと対応の緊急性

vCenter Serverは企業のVMware仮想化環境全体を管理するWebベースの中枢コンポーネントであり、侵害された場合、配下の仮想マシン群やストレージ・ネットワーク基盤全体への影響が及ぶ可能性がある。認証不要でネットワークからアクセス可能な深刻度9.8の脆弱性であることから、セキュリティ研究者らはインターネットに露出したvCenter管理インターフェースの即時パッチ適用を強く推奨している。なお、vSphere 8.0 Update 3kの適用によりVCF 9.1へのアップグレードパスが一時的にブロックされる既知の問題も報告されている。

---

## 関連記事

なし（新規トピック）
