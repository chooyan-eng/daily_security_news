# Abbott Laboratories、Exact Sciences旧システムとLabCentralポータルで二重のサイバー侵害を調査

- **日付**: 2026-07-18
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/abbott-laboratories-probes-two-cyber-incidents-amid-extortion-claims/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

医療機器・診断薬大手 Abbott Laboratories が、2件の別々のサイバーインシデントを調査していると公表した。1つはがん診断事業部門（旧Exact Sciences）のレガシーシステムへの不正アクセスで、恐喝グループ ShinyHunters が同社をデータリークサイトに掲載し7月18日以降のデータ公開を予告した。もう1つはLabCentral顧客ポータルへの侵害で、侵害された顧客認証情報を利用した侵入と見られる。

## 詳細

### Exact Sciences（がん診断事業）インシデント

AbbottはがんCancer Diagnostics事業における、旧Exact Sciences社の内部レガシーシステムへの不正アクセスを確認した。恐喝グループ ShinyHunters は自身のデータリークサイトにAbbottを掲載し、当初は7月18日以降、身代金交渉に応じない場合に窃取したとされるデータを公開すると脅迫していた。Abbott はこの事業単位以外の他事業・拠点・システムには影響がなく、旧Exact Sciencesシステムは Abbott の本体システムとは分離されていたと説明している。

### LabCentralポータルのインシデント

もう一方の脅威アクターは、侵害された顧客認証情報を用いてLabCentral顧客ポータルへの侵入経路（環境内の「弱点」と説明）を悪用したとされる。窃取が主張されているデータには、CE製造証明書、操作マニュアル、技術仕様書、規制関連文書、製品要求仕様アーカイブ、キャリブレーター値割当、アッセイファイルなど、製品関連の文書が含まれる。

### 会社の対応

Abbottは、事業やカスタマーへの影響はなく、機密性の高い顧客・事業情報の流出も確認されていないと述べている。両インシデントとも現在進行中の調査対象である。

### ShinyHuntersとの関連性

ShinyHuntersは2026年5月〜6月にOracle PeopleSoftのゼロデイ脆弱性（CVE-2026-35273）を悪用し、大学等100社以上に侵入したキャンペーンで知られる恐喝グループである。今回のAbbott/Exact Sciences事案は同一の脆弱性悪用によるものかは明らかになっていないが、同一の脅威アクターによる企業データの恐喝という点で軌を一にしており、同グループの活動が継続・拡大していることを示している。

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一の脅威アクター（ShinyHunters）による恐喝キャンペーン
