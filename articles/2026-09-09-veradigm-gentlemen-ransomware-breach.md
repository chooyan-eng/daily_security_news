# 米医療IT大手Veradigm、委託ベンダー経由の侵害で患者データ流出 The Gentlemenが犯行主張

- **日付**: 2026-09-09
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/veradigm-discloses-patient-data-breach-after-gentlemen-gang-claims-attack/), [The Record](https://therecord.media/electronic-health-record-company-says-customer-data-stolen-in-breach)
- **トピック**: [TheGentlemen ランサムウェアグループ（2026年）](../topics/thegentlemen-ransomware-2026.md)
- **分類**: 続報

## 概要

米医療IT大手Veradigm Inc.は2026年9月8日、SEC（米証券取引委員会）への開示文書で、委託先ベンダーのシステムを経由した侵害により、社会保障番号を含む患者の機微情報が流出したと公表した。ランサムウェアグループ「The Gentlemen」が犯行を主張している。

## 詳細

Veradigmによれば、攻撃者はVeradigm自身のインフラを直接侵害したのではなく、委託先ベンダーの環境内からログイン認証情報を窃取した。この認証情報を使って、当該ベンダーがVeradigmの医療機関顧客向けにサービス提供のために利用していた特定のVeradigm API へ不正アクセスが行われた。

脅威アクターは、患者の氏名・住所・社会保障番号（SSN）・メールアドレス・電話番号に加え、保証人（guarantor）の個人識別情報を含む、約350万件の患者記録を保有していると主張している。ただし、臨床記録や診療内容そのものといった医療情報（クリニカルデータ）は今回の侵害の対象に含まれていないとされる。

本件はランサムウェアグループ「The Gentlemen」が犯行を主張したことを受けてVeradigmが調査を開始し、侵害の事実を確認したもの。The Gentlemenは2025年中旬に台頭した急成長中のRaaS（Ransomware-as-a-Service）グループで、2026年だけで240件を超える被害を主張しており、被害者数ベースで世界第2位の規模を持つランサムウェアグループとされる。製造・エネルギー・防衛セクターへの攻撃に加え、境界防御機器（Check Point・Cisco製ファイアウォール等)のCVEやConnectWise ScreenConnectの悪用を通じた侵入を得意としてきたが、今回は医療IT分野のサプライチェーン（委託ベンダー経由の認証情報窃取）を突いた侵害である点が特徴的である。

Veradigmはインシデント対応手順を発動し法執行機関へ通報するとともに、影響範囲の精査と対象顧客・個人への通知、該当者への信用監視サービス提供を開始している。医療機関にサービスを提供するベンダーのAPIアクセス管理・認証情報の管理体制が、間接的な侵害経路として今後も狙われる可能性が示唆される。
