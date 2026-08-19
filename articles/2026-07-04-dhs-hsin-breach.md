# 米国土安全保障省の情報共有基盤HSINに不正侵入、ワールドカップ警備調整情報が数週間閲覧可能な状態に

- **日付**: 2026-07-01
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/dhs-confirms-hackers-breached-hsin-info-sharing-platform/)、[TechCrunch](https://techcrunch.com/2026/07/02/us-government-says-it-got-hacked-again/)、[UpGuard](https://www.upguard.com/news/department-of-homeland-security-data-breach-2026-07-01)
- **トピック**: [米国土安全保障省 情報共有基盤HSIN不正侵入（2026年）](../topics/dhs-hsin-breach-2026.md)
- **分類**: 新規

## 概要

米国土安全保障省（DHS）は、連邦・州・民間機関間の脅威情報共有基盤HSINおよび協業用SharePointシステムが2026年5月末〜6月上旬に不正アクセスを受けたと発表した。FIFAワールドカップなど大型イベントの警備調整データを含む非機密情報が、数週間侵入に気づかれないまま閲覧可能な状態に置かれていた。

## 詳細

### 事案の概要

DHSが運用するHomeland Security Information Network（HSIN）は、連邦・州・地方自治体・民間セクターの関係機関が脅威情報や警備計画を共有するための基盤である。2026年5月末から6月上旬にかけて、このHSINサーバーおよび協業用SharePointシステムに対する不正アクセスが発生し、7月1日にDHSが公表した。

### 影響範囲

DHSは、機密（classified）情報系統への影響はないとしているが、非機密（unclassified）階層に保管されていたセキュリティ計画・イベント調整情報が外部から閲覧可能な状態にあった可能性がある。具体的には、FIFAワールドカップなど大規模イベントの警備調整に関するデータが含まれていたとされる。

### 発覚までの経緯

侵入は5月末から6月上旬にかけて発生したとみられ、外部への公表は7月1日と、発覚まで数週間を要した。攻撃者の身元・帰属については現時点で未確定であり、特定の国家主体との関連付けはなされていない。

### 調査状況

DHSはフォレンジック調査を継続中で、データが外部に持ち出されたか否かについても調査中としている。米上院議員からは司法省による捜査を求める声も上がっている。

### SharePoint関連脆弱性との関連性（推測）

本事案では協業用SharePointシステムも標的となったとされているが、同時期に報告されているMicrosoft SharePoint Serverの重大RCE脆弱性CVE-2026-45659の悪用キャンペーンとの直接的な関連は現時点で確認されていない。政府機関のSharePoint基盤が相次いで標的にされている点は注視すべき傾向といえる。

---

## 関連記事

なし（新規トピック）
