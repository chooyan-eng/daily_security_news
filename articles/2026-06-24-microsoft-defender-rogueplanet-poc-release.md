# Microsoft Defender RoguePlanet（CVE-2026-50656）：研究者がPoC公開、パッチ済みWindows 10/11でのSYSTEM権限奪取を実証

- **日付**: 2026-06-24
- **出典**: [SecurityWeek](https://www.securityweek.com/microsoft-working-on-patch-for-rogueplanet-zero-day/)
- **トピック**: [Microsoft Defender RoguePlanet ゼロデイ（CVE-2026-50656）](../topics/microsoft-defender-rogueplanet-2026.md)
- **分類**: 続報

## 概要

Microsoft Defender の RoguePlanet ゼロデイ（CVE-2026-50656）において、発見者「Nightmare Eclipse」が概念実証（PoC）エクスプロイトを公開した。最新の 2026年6月パッチ適用済みの Windows 10/11 においても SYSTEM 権限へのローカル特権昇格（LPE）が可能なことを実証しており、悪用リスクが大幅に高まっている。Microsoft は引き続きパッチを開発中。

## 詳細

### PoC 公開の経緯

CVE-2026-50656（RoguePlanet）は2026年6月10日に Nightmare Eclipse（別名 Chaotic Eclipse）が最初に公開したゼロデイ。今回、同研究者が完全動作する PoC エクスプロイトコードをリリース。

- **公開された PoC**: ローカル特権昇格（LPE）を実際に示すエクスプロイトコード
- **対象環境**: 最新の 2026年6月パッチ（KB5094126）を適用した Windows 10 および Windows 11
- **権限**: NT AUTHORITY\SYSTEM（最高権限）のコマンドシェルを起動可能

### 脆弱性の技術的詳細（再確認）

- **種別**: TOCTOU（Time-of-Check to Time-of-Use）競合状態
- **対象コンポーネント**: Windows Defender Malware Protection Engine
- **CVSS**: 7.8（Important）
- **前提条件**: ローカルアクセス可能な標準ユーザーアカウント

悪用のシナリオ：既に何らかの手段（フィッシング、ウェブ悪用等）で標準ユーザーとしてシステムにアクセスした攻撃者が、この PoC を実行することで SYSTEM 権限に昇格し、完全な制御を獲得できる。

### PoC 公開による影響

PoC の公開により、高度な技術力を持たない攻撃者（スクリプトキディ等）でも脆弱性を悪用できるようになった。Microsoft はパッチを開発中と説明しているが、提供時期は依然未定。Defender は Windows に標準搭載された主要セキュリティ製品であるため、悪用リスクは特に深刻。

### 現状と緩和策

Microsoft のパッチは未提供。推奨される一時的緩和策：
- 不要なローカルユーザーアカウントを削除・無効化
- エンドポイントの EDR 製品で異常なプロセス生成（特に SYSTEM 権限プロセスの親プロセスが Defender サービス）を検知
- ローカル管理者権限の最小化（標準ユーザーとして運用）

---

## 関連記事

（続報のため関連記事セクションは省略）
