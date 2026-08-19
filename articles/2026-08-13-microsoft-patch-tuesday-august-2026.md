# Microsoft 2026年8月Patch Tuesday：Lazarus悪用のWinSockゼロデイとSharePoint RCEチェーンを修正

- **日付**: 2026-08-13
- **出典**: [SecurityWeek](https://www.securityweek.com/august-2026-patch-tuesday-microsoft-fixes-421-cves-one-exploited-zero-day/), [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-august-2026-patch-tuesday-fixes-400-flaws-3-zero-days/), [The Hacker News](https://thehackernews.com/2026/08/lazarus-exploits-windows-zero-day-to.html), [The Register](https://www.theregister.com/security/2026/08/11/421-bugs-in-microsofts-patch-tuesday-release-and-the-norks-have-already-attacked-one/5286483)
- **トピック**: [Microsoft Patch Tuesday 2026年8月](../topics/microsoft-patch-tuesday-august-2026.md)
- **分類**: 新規

## 概要

Microsoftは2026年8月11日、月例セキュリティ更新で421件のCVEを修正した。うち、WindowsのWinSockカーネルドライバ（afd.sys）に存在する権限昇格ゼロデイCVE-2026-68820は、北朝鮮系脅威アクターLazarusによる積極的悪用が確認されている。また、SharePointのRCE脆弱性チェーンを構成するCVE-2026-63520も同時に修正された。

## 詳細

### 修正規模

2026年8月のPatch Tuesdayでは421件のCVEが修正され、うちCritical評価は62件、悪用が確認済みのゼロデイが1件、情報が公開済みのゼロデイが3件含まれる。

### CVE-2026-68820：Lazarusが悪用するWinSockゼロデイ

CVE-2026-68820は、Windows Sockets APIの基盤となるカーネルモードドライバ「Ancillary Function Driver for WinSock（afd.sys）」に存在するuse-after-free脆弱性。悪用に成功するとSYSTEM権限への昇格が可能になる。

Check Point Researchの調査により、本脆弱性の悪用は北朝鮮の脅威アクターLazarusグループに帰属するとされ、2026年7月初旬から防衛関連企業を標的とした「Operation Dream Job」キャンペーンの一環として、FudModuleルートキットおよびForestTigerバックドアの展開に利用されていたことが判明した。

CISAは本脆弱性をKnown Exploited Vulnerabilities（KEV）カタログに追加し、連邦機関に対し2週間以内のパッチ適用を義務付けている。対応するパッチはWindows 11向けKB5121003、Windows 10向けKB5120249として提供されている。

### CVE-2026-63520：SharePoint RCEチェーン

CVE-2026-63520はMicrosoft SharePointのBusiness Connectivity Servicesにおける安全でない.NET型インスタンス化に起因するRCE脆弱性（CVSSv3.1で8.1）。Rapid7とMicrosoftが共同で開示した。単独では認証が必要だが、以前に開示された認証バイパスの脆弱性CVE-2026-55040と連鎖させることで、未認証のリモートコード実行が可能になるエクスプロイトチェーンを構成する。

本稿執筆時点でCVE-2026-63520単体の実運用環境での悪用は確認されていないが、Microsoftは「悪用の可能性が高い」と評価しており、Proof-of-Conceptが公開され次第、急速に悪用が広がるリスクがあるとして早期のパッチ適用が推奨されている。

### 対応の推奨

- Windows端末: KB5121003（Windows 11）/ KB5120249（Windows 10）を最優先で適用
- SharePoint Server: 8月更新プログラムを適用し、CVE-2026-55040との連鎖悪用に備える
- 防衛関連・重要インフラ組織は、Lazarusによる悪用実績を踏まえ、afd.sys関連の侵害兆候（FudModule・ForestTiger）を優先的に調査する

---

## 関連記事

なし（新規トピック）
