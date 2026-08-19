# Ubiquiti、UniFi Connect/Talk/Access に最大深刻度10.0を含む7件の重大脆弱性 — わずか数日で3回目の大量開示

- **日付**: 2026-07-08
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/ubiquiti-warns-of-new-max-severity-unifi-os-vulnerability/)
- **トピック**: [Ubiquiti UniFi OS 最大深刻度脆弱性の悪用（2026年6月）](../topics/ubiquiti-unifi-os-vulnerabilities-2026.md)
- **分類**: 関連

## 概要

Ubiquitiは2026年7月8日、Security Advisory Bulletin 066にて UniFi Connect・Talk・Access・Protect アプリケーションおよび UniFi OS 本体に存在する7件の重大脆弱性を公開した。最も深刻な CVE-2026-50746（CVSS 10.0）は UniFi Connect の不適切なアクセス制御によるコマンドインジェクションで、認証不要・ネットワークアクセスのみで悪用可能。6月の UniFi OS Server 悪用（CVE-2026-34908等）とは別のCVE群だが、同社製品全体で短期間に脆弱性開示が相次いでいる。

## 詳細

### 主な脆弱性

**CVE-2026-50746**（CVSS 10.0・最大深刻度）
- 種別: 不適切なアクセス制御（Improper Access Control）
- 対象: UniFi Connect Application 3.4.16以前
- 内容: ネットワークアクセスのみで認証不要のコマンドインジェクションが可能。攻撃複雑度低・特権不要・ユーザー操作不要。
- 修正: 3.4.20以降

**CVE-2026-50747**（CVSS 9.9）
- 種別: 認証済みSQLインジェクション
- 対象: UniFi Talk Application 5.1.2以前
- 内容: 低権限のネットワークアクセスを持つ攻撃者がホストデバイス上で権限昇格可能
- 修正: 5.2.2以降

**CVE-2026-50748**（CVSS 9.9）
- 種別: 不適切な入力検証によるコマンドインジェクション
- 対象: UniFi Access Application 4.2.28以前
- 内容: 低権限でホスト上のコマンドインジェクションが可能
- 修正: 4.2.29以降

同時に UniFi Talk・Access・Protect アプリケーション、UniFi OS Server、および UDM・UNVR・UNAS 系デバイス全般にまたがる4件の追加の重大脆弱性（CVE-2026-54400、CVE-2026-54402、CVE-2026-55115、CVE-2026-55116）も修正されている。

### 開示の背景

今回のBulletin 066は、7月7日以降に発生した「3日連続」のUbiquiti脆弱性開示の一環であり、この期間で新規に開示された重大CVEは合計14件に達した。同社は7月2日にもBulletin 066で25件の脆弱性（UniFi Connect・Talk・Access・Protect・Network対象）をまとめて公開している。CVSS 10.0のCVE-2026-50746は約10万台のエンドポイントに影響するとの推計もある。

### 悪用状況

現時点でUbiquitiはこれらの脆弱性が実際の攻撃で悪用されたかどうかを確認していない。ただし6月に悪用が確認された UniFi OS Server の3脆弱性（CVE-2026-34908/34909/34910）では大学・高等教育機関が主要標的となっており、UniFi製品群への継続的な攻撃者の関心がうかがえる。

### 対策

- UniFi Connect を 3.4.20 以降に更新
- UniFi Talk を 5.2.2 以降に更新
- UniFi Access を 4.2.29 以降に更新
- 管理インターフェースへのネットワークアクセスを制限し、インターネットへの直接露出を避ける

---

## 関連記事

- [Ubiquiti UniFi OS 最大深刻度脆弱性の悪用（2026年6月）](../topics/ubiquiti-unifi-os-vulnerabilities-2026.md) - 同一ベンダーのUniFi製品群における脆弱性開示・悪用の継続
