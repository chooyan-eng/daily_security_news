# Broadcom、VMware vCenter/ESXの重大脆弱性3件を含む計5件を修正（認証バイパス・VMエスケープ）

- **日付**: 2026-07-29
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/vmware-fixes-three-critical-flaws-allowing-auth-bypass-vm-escapes/)
- **トピック**: [VMware vCenter/ESX 重大脆弱性 VMSA-2026-0006（2026年）](../topics/vmware-vcenter-esx-critical-vulnerabilities-2026.md)
- **分類**: 新規

## 概要

BroadcomはVMware Security Advisory VMSA-2026-0006にて、vCenter ServerおよびESXiに影響する5件の脆弱性を修正した。うち3件が重大（Critical）に分類され、認証バイパスによる管理者権限奪取（CVE-2026-59309）、リモートコード実行（CVE-2026-59310）、仮想マシンエスケープ（CVE-2026-47876）が含まれる。

## 詳細

### 脆弱性の技術的詳細

**アドバイザリ**: VMSA-2026-0006（2026年7月29日公開）

1. **CVE-2026-59309**（Critical）: VMware Directory Serviceにおける認証バイパス。vCenterのネットワークに到達可能な攻撃者が、細工したリクエストを送信することでログインチェックを回避し、管理者権限で不正アクセスできる。

2. **CVE-2026-59310**（Critical、CVSS 9.8）: vCenter Serverにおける脆弱性。ネットワークアクセス権を持つ攻撃者が任意コードを実行できる。

3. **CVE-2026-47876**（Critical、CVSS 9.3）: VMXNET3仮想ネットワークアダプタを標的とした脆弱性。ゲスト仮想マシンと基盤となるESXiホストとの間の分離を破り、VMエスケープが成立し得る。

このほか2件の非Critical脆弱性も同時に修正されている。

### 修正バージョン

- vCenter: 9.1.0.0300、9.0.2.0100、8.0 Update 3k
- ESXi: 9.1.0.0200、9.0.2.0100、8.0 Update 3k

### 仮想化基盤への影響

vCenter/ESXiは多数の企業においてWebアプリケーション・データベースを含む仮想マシン群のホスト基盤として利用されている。特にCVE-2026-59309の認証バイパスとCVE-2026-59310のRCEが組み合わされた場合、仮想化基盤全体の掌握に至るリスクがあり、影響範囲はホストされる個々のWebサービス全体に及ぶ。VMエスケープ（CVE-2026-47876）は、マルチテナント環境における他テナントの仮想マシンへの侵害拡大にもつながり得る。

### 対応の緊急性

いずれも重大度が高く、公開情報をもとにした悪用コードの出現が懸念されるため、該当バージョンを利用する組織は速やかなパッチ適用が推奨される。

---

## 関連記事

なし（新規トピック）
