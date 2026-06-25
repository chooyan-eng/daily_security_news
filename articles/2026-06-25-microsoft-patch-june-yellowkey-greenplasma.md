# Microsoft Patch Tuesday 2026年6月: YellowKey・GreenPlasma・MiniPlasma ゼロデイ詳細分析

- **日付**: 2026-06-25
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-patches-yellowkey-greenplasma-miniplasma-zero-days/)
- **トピック**: [Microsoft Patch Tuesday 2026年6月](../topics/microsoft-patch-tuesday-june-2026.md)
- **分類**: 続報

## 概要

2026年6月10日のMicrosoft Patch Tuesday で修正された3件の公開済みゼロデイ脆弱性（YellowKey・GreenPlasma・MiniPlasma）の詳細分析が報告された。研究者「Nightmare Eclipse（別名：Chaotic Eclipse）」が発見・公開したこれらの脆弱性は、BitLocker バイパスおよびローカル特権昇格（LPE）を可能にし、完全パッチ済み Windows 10/11 および Windows Server 2022/2025 に影響する。

## 詳細

### 3件のゼロデイ概要

| 脆弱性名 | CVE | CVSS | 種別 | 対象コンポーネント |
|---------|-----|------|------|----------------|
| YellowKey | CVE-2026-45585 | 未公開 | BitLocker バイパス | Windows Recovery Environment（WinRE） |
| GreenPlasma | CVE-2026-45586 | 未公開 | LPE（SYSTEM権限）| Collaborative Translation Framework（CTFMON） |
| MiniPlasma | CVE-2020-17103 | 未公開 | LPE（SYSTEM権限）| Cloud Files Mini Filter Driver |

### YellowKey（CVE-2026-45585）— BitLocker バイパス

**攻撃シナリオ**: 物理的アクセスを持つ攻撃者が、未修正の Windows 11 および Windows Server 2022/2025 デバイスの BitLocker 暗号化をバイパスし、保護されたドライブのコンテンツにフルアクセスできる。

**悪用方法**: Windows Recovery Environment（WinRE）の動作を意図的に利用したバックドア的な動作として機能する。BitLocker が有効であっても、WinRE の特定の状態遷移においてドライブが復号された状態で利用可能になる瞬間を悪用する。

**前提条件**: デバイスへの物理的アクセス（盗難デバイス・国境通過時の検査・内部脅威等）

**影響範囲**: 完全パッチ済み Windows 11 および Windows Server 2022/2025（追加の緩和措置が必要）

### GreenPlasma（CVE-2026-45586）— CTFMON LPE

**攻撃シナリオ**: 低権限ユーザーが CTFMON.exe（Collaborative Translation Framework、テキスト入力・音声・IME サービスを処理）の脆弱性を悪用し、完全なSYSTEM権限を取得する。

**特徴**: 完全パッチ済みの Windows 10/11 において有効。標準的なユーザー権限から SYSTEM への特権昇格（Privilege Escalation）を可能にする。

### MiniPlasma（CVE-2020-17103）— Cloud Files Mini Filter Driver LPE

**攻撃シナリオ**: GreenPlasma と同様に SYSTEM 特権への昇格を可能にするが、Cloud Files Mini Filter Driver（OneDrive 等のクラウドファイル同期機能と統合されたカーネルドライバー）を標的とする。

### 発見者と開示経緯

研究者「Nightmare Eclipse」（別名「Chaotic Eclipse」）がこれら3件の脆弱性を発見・公表し、PoC（概念実証）コードも公開した。Microsoft は6月10日の Patch Tuesday で全件の正式パッチを提供するとともに、YellowKey に対する追加緩和措置も共有している。

### 他のゼロデイとの関連

同研究者は Microsoft Defender の RoguePlanet（CVE-2026-50656）も発見しており、パッチ未提供の状態が続いている。Windows エコシステムの複数コンポーネントにまたがる連続したゼロデイ発見は、この研究者グループが Windows の根幹的なセキュリティコンポーネントに深い知識を持つことを示している。

---

## 関連記事

なし
