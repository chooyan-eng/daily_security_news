# 11件のMicrosoft署名済みUEFIシムがSecure Bootをバイパス可能と判明

- **日付**: 2026-07-14
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/11-old-microsoft-signed-linux-uefi.html), [ESET WeLiveSecurity](https://www.welivesecurity.com/en/eset-research/forgotten-uefi-shims-undermining-secure-boot/), [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/uefi-shims-secure-boot-bypass/)
- **トピック**: [UEFIシムによるSecure Bootバイパス（CVE-2026-8863/CVE-2026-10797）](../topics/uefi-secure-boot-bypass-shims-2026.md)
- **分類**: 新規

## 概要

セキュリティ研究者が、Microsoftによって過去に署名されたオープンソースshimプロジェクトの古いUEFIアプリケーション11件に、Secure Bootをバイパスできる脆弱性（CVE-2026-8863、CVE-2026-10797）を発見した。バージョン0.9以下の古いshimバイナリが対象で、ブート時に未検証コードを実行させることでBootkitty・HybridPetya・BlackLotusのような悪意あるUEFIブートキットの展開を可能にする。Microsoftは責任ある開示を受け、2026年6月のPatch Tuesdayでdbx（失効リスト）更新により該当バイナリを失効させた。

## 詳細

### 発見の経緯

発見したのはESET Researchで、2026年2月の責任ある開示を経て、Microsoftが6月9日のPatch Tuesdayで脆弱なバイナリをdbx（UEFI失効データベース）に追加し失効させた。今回の報道はこの調査結果の詳細分析として複数メディアが取り上げたもの。

### 技術的詳細

対象となった11件のshimは、いずれもバージョン0.9以下で、Microsoftの「Microsoft Corporation UEFI CA 2011」というサードパーティ証明書によって署名されている。この証明書を信頼するUEFIシステムであれば、インストールされているOSの種類を問わず、これらのバイナリを正規のものとして受け入れてしまう。

攻撃者に高度なエクスプロイト技術は不要で、古い失効前のshimバイナリのコピーと、UEFIシムの動作に関する基本的な理解さえあれば、Secure Bootという基幹的なセキュリティ機能をバイパスできてしまう点が深刻とされる。

### 影響

攻撃者はブートプロセス中に未検証のコードを実行できるようになり、Bootkitty、HybridPetya、BlackLotusといった既知の悪意あるUEFIブートキットを、Secure Bootが有効化されたシステム上でも展開可能になる。これらのブートキットはOS起動前のファームウェアレベルで動作するため、OS側のセキュリティ対策では検知・除去が困難という特性を持つ。

### 対応

Microsoftは6月9日のPatch Tuesdayで該当する脆弱なバイナリをdbx更新により失効させ済み。ただし、dbx更新が適用されていない、または適用できないシステムでは引き続きリスクが残る。企業・組織は自社のUEFIファームウェアが最新のdbx失効リストを適用済みか確認することが推奨される。

---

## 関連記事

なし（新規トピック）
