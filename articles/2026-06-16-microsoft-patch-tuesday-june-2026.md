# Microsoft Patch Tuesday 2026年6月：過去最多206件の脆弱性を修正、3つのゼロデイ含む

- **日付**: 2026-06-16
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-june-2026-patch-tuesday-fixes-6-zero-days-200-flaws/)
- **トピック**: [Microsoft Patch Tuesday 2026年6月](../topics/microsoft-patch-tuesday-june-2026.md)
- **分類**: 新規

## 概要

Microsoftは2026年6月10日（日本時間）に過去最多となる206件の脆弱性を修正するPatch Tuesdayをリリースした。うち39件がCritical、3件が悪用実績のあるゼロデイ。WindowsカーネルRCEのCVE-2026-45657（CVSS 9.8）をはじめ、Remote Desktop Client、Hyper-V、Officeなど広範な製品に深刻な脆弱性が含まれる。

## 詳細

### 全体規模

- 修正件数：206件（単月として過去最多記録）
- Critical：39件（うちRCEが28件）
- ゼロデイ（公開前に悪用確認または公開済み）：3件

### 主要なCritical脆弱性

#### CVE-2026-45657: Windows Kernel RCE（CVSS 9.8）
- Windowsカーネルのuse-after-free脆弱性
- ネットワーク経由・認証不要・ユーザー操作不要でのRCEが可能
- TCP/IPデータ処理の欠陥を悪用してSYSTEMレベルのコード実行が可能
- 対象：Windows 11 23H2〜26H1、Windows Server 2022/2025
- **ワーム可能（Wormable）**と評価される

#### Remote Desktop Client（11件のCVE）
- CVE-2026-44801、CVE-2026-44799、CVE-2026-42992、CVE-2026-42985がCritical RCE
- クライアント側で悪意あるRDPサーバーに接続するだけで攻撃が成立

#### Windows Hyper-V（3件のCritical RCE）
- CVE-2026-47652、CVE-2026-45641、CVE-2026-45607
- VMゲストからホストへのエスケープとコード実行が可能

#### Microsoft Office
- CVE-2026-45458（Outlook）、CVE-2026-45456（Word）がCritical RCE
- 悪意あるドキュメントをメールで配信する手口が想定される

#### その他の注目CVE
- **CVE-2026-42904**：TCP/IP脆弱性
- **CVE-2026-44815**：DHCP Server RCE
- **CVE-2026-47291**：HTTP.sysに対するDoS脆弱性

### 攻撃チェーンのリスク

RCE（コード実行）と特権昇格（EoP）の脆弱性を組み合わせることで、単一の脆弱性悪用から完全なシステム制御に至る攻撃チェーンが構築される点が最大のリスク。

### IPA・組織向け推奨対応

- 月例アップデートを速やかに適用
- 特にWindows Kernel（CVE-2026-45657）はワーム可能と評価されており最優先で対応
- Remote Desktop Clientを使用している環境は即時パッチ適用
- Microsoft Exchange、Officeも対象のため全社的なパッチ管理が必要

---

## 関連記事

なし
