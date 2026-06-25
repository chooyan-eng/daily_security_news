# Microsoft Defender RoguePlanet ゼロデイ（CVE-2026-50656）

## 概要

研究者「Nightmare Eclipse」（別名「Chaotic Eclipse」）が2026年6月10日に公開した Windows Defender のゼロデイ脆弱性。CVE-2026-50656 として登録（CVSS 7.8）。Defender の Malware Protection Engine に存在する TOCTOU（Time-of-Check to Time-of-Use）競合状態を悪用し、完全パッチ済みの Windows 10/11 でも NT AUTHORITY\SYSTEM 権限を持つコマンドシェルを起動できる。Microsoft はパッチ開発中だが提供時期未定。

**同一性の判断に役立つ情報：**
- CVE: CVE-2026-50656
- 別名: RoguePlanet
- 種別: ローカル特権昇格（LPE）/ TOCTOU 競合状態
- 対象コンポーネント: Windows Defender Malware Protection Engine
- CVSS: 7.8（Important）
- 影響: 完全パッチ済み Windows 10/11（KB5094126 適用済みを含む）
- 発見者: Nightmare Eclipse / Chaotic Eclipse
- 公開日: 2026-06-10（MSRC 登録: 2026-06-16）
- パッチ状況: 未提供（Microsoft 開発中）

## タイムライン

- [2026-06-25 Microsoft Defender RoguePlanet（CVE-2026-50656）— パッチ未提供の状態が継続、SecurityWeek が現状を報告](../articles/2026-06-25-microsoft-defender-rogueplanet-securityweek.md)
- [2026-06-24 Microsoft Defender RoguePlanet（CVE-2026-50656）：研究者がPoC公開、パッチ済みWindows 10/11でのSYSTEM権限奪取を実証](../articles/2026-06-24-microsoft-defender-rogueplanet-poc-release.md)
- [2026-06-18 Microsoft Defender ゼロデイ「RoguePlanet」（CVE-2026-50656）：パッチ済み Windows で SYSTEM 特権を奪取](../articles/2026-06-18-microsoft-defender-rogueplanet-cve-2026-50656.md)
