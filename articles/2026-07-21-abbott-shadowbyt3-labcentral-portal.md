# Abbott傘下Core Laboratory、SHADOWBYT3$がLabCentralポータルへの侵害を主張

- **日付**: 2026-07-21
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/abbott-laboratories-probes-two-cyber-incidents-amid-extortion-claims/)
- **トピック**: [SHADOWBYT3$ ランサムウェアグループ・Nintendo 侵害（2026年6月）](../topics/nintendo-shadowbyt3-breach-2026.md)
- **分類**: 続報

## 概要

Abbott Laboratoriesは、傘下のCore Laboratory診断事業が運営する顧客向けポータル「LabCentral」に対する不正アクセスを調査していると明らかにした。恐喝グループSHADOWBYT3$は、侵害した顧客の認証情報を用いてポータルの「弱点」を突き、APIエンドポイントを標的にファイルを段階的に窃取したと主張している。

## 詳細

### 攻撃手法

SHADOWBYT3$は、侵害済みの顧客認証情報を使ってLabCentralポータルへログインし、環境内の「弱点（weak point）」を特定したと主張。2026年7月4日にアクセスを獲得した後、APIエンドポイントを標的として時間をかけてファイルを段階的に外部へ持ち出した（低速なexfiltration）としている。

### Abbottの見解

Abbottは、このサードパーティホスティングのポータルには機微情報は含まれておらず、操作マニュアルや製品仕様書、トラブルシューティングチェックリストといった、公開情報に相当する非機密の技術資料のみが保管されていると主張している。

### 事業への影響

Abbottによれば、本件がAbbottの他事業に波及した形跡はなく、事業運営・製品供給・製造/検査業務・患者対応能力への影響も確認されていない。

### 既存トピックとの関係

SHADOWBYT3$は2026年6月、従業員エンゲージメントSaaS「TinyPulse」のクラウド環境を経由してNintendo of Americaの従業員データ859MBを窃取したと主張し、200万米ドルの身代金を要求した恐喝グループ。今回はAbbott傘下Core Laboratoryの顧客ポータルという別の標的・別の侵入経路(認証情報侵害によるポータルアクセス)で活動しており、同一の恐喝アズ・ア・サービスグループによる新たな攻撃として位置づけられる。

---

## 関連記事

なし
