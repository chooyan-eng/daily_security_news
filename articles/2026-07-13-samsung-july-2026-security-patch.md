# Samsung、2026年7月のセキュリティパッチで57件の脆弱性を修正 — 重大5件を含む

- **日付**: 2026-07-13
- **出典**: [SammyGuru](https://sammyguru.com/samsung-july-2026-security-patch-details/), [SamMobile](https://www.sammobile.com/news/samsung-july-2026-security-patch-detailed/)
- **トピック**: [Samsung 2026年7月セキュリティパッチ](../topics/samsung-july-2026-security-patch.md)
- **分類**: 新規

## 概要

Samsungは2026年7月7日、Galaxyシリーズ向けの月例セキュリティパッチをリリースし、合計57件の脆弱性を修正した。内訳はGoogleが提供するAndroid Security Bulletin（ASB）由来の41件と、Samsung独自のSVE（Samsung Vulnerabilities and Exposures）16件。重大（Critical）脆弱性5件、高（High）42件、中（Moderate）7件を含む。対象はAndroid 14・15・16を搭載する端末で、Galaxy S26シリーズなど一部端末から順次配信が始まっている。

## 詳細

### 修正件数の内訳

- 合計: 57件
- Google提供のASB由来: 41件（うち重大5件、高36件）
- Samsung独自のSVE: 16件（うち高6件、中程度7件、非公開扱い分を含む）
- 深刻度別合計: 重大5件、高42件、中程度7件

### 重大（Critical）脆弱性

重大に分類された脆弱性としてCVE-2026-27280、CVE-2026-28590、CVE-2026-28618、CVE-2026-28639、CVE-2026-33636が挙げられている。詳細な技術的内容は多くが非公開だが、いずれもリモートでの悪用可能性が高いと評価されている。

### 注目のSamsung独自脆弱性（SVE）

画像コーデックライブラリ関連で新たにSVE-2026-1087・SVE-2026-1650が追加された。あわせて、Adobe DNG SDKに由来する重大な脆弱性も本パッチで対応されている。一部のSVE項目については、Samsungの方針により詳細が非公開となっている。

### 配信状況

Galaxy Z Fold 7・Galaxy Z Flip 7では、重大な画像ファイル関連のエクスプロイトを修正するアップデートとして7月10日前後に配信が確認されている。Galaxy S26シリーズが最初にこのセキュリティアップデートを受け取る端末群とされ、他機種にも順次展開される見込み。

### 対策

- Galaxy端末のユーザーは設定画面からソフトウェア更新を確認し、2026年7月以降のセキュリティパッチレベルへ速やかに更新すること
- 企業でGalaxy端末を利用している場合、MDM経由でのパッチ適用状況の可視化・強制適用を検討すること
