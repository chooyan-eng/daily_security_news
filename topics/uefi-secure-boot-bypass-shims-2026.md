# UEFIシムによるSecure Bootバイパス（CVE-2026-8863/CVE-2026-10797）

## 概要

ESET Researchが発見した、Microsoft署名済みの古いオープンソースUEFIシム（バージョン0.9以下）11件に存在するSecure Bootバイパス脆弱性（CVE-2026-8863、CVE-2026-10797）。攻撃者はブート時に未検証コードを実行させ、Bootkitty・HybridPetya・BlackLotusなどの悪意あるUEFIブートキットを、Secure Boot有効環境でも展開可能。2026年2月に責任ある開示、Microsoftは6月9日のPatch Tuesdayでdbx更新により失効済み。

**同一性の判断に役立つ情報：**
- CVE: CVE-2026-8863、CVE-2026-10797
- 発見組織: ESET Research
- 開示日: 2026年2月（責任ある開示）
- 対策実施日: 2026年6月9日（Microsoft dbx更新）
- 対象: Microsoft Corporation UEFI CA 2011で署名された旧shimバイナリ（v0.9以下）11件

## タイムライン

- [2026-07-14 11件のMicrosoft署名済みUEFIシムがSecure Bootをバイパス可能と判明](../articles/2026-07-15-uefi-secure-boot-bypass-shims.md)
