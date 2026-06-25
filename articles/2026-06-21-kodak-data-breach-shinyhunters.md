# Kodak データ侵害確認 — ShinyHunters が220万件の顧客・企業データ流出を主張

- **日付**: 2026-06-21
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/kodak-confirms-data-breach-claimed-by-shinyhunters-extortion-gang/) / [CyberNews](https://cybernews.com/security/shinyhunters-claims-kodak-hack-2-million-records/) / [CyberSecurityNews](https://cybersecuritynews.com/kodak-confirms-data-breach/)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

画像技術大手 Kodak が、ShinyHunters によるハッキングを受けた事実を公式に認めた。ShinyHunters は220万件超の顧客データ・社内データを盗んだと主張し、2026年6月15日にダークウェブで告知。Kodak は「限られた量のデータへの一時的なアクセス」を確認しながらも、主張規模の独立検証はできていないと述べた。なお、Kodak 社の基幹システムへの継続的な脅威はないとしている。

## 詳細

### 侵害の概要

| 項目 | 詳細 |
|------|------|
| 発覚日 | 2026年6月15日（ShinyHunters がダークウェブに掲載） |
| 主張規模 | 220万件超（顧客個人情報・社内データ） |
| 脅迫期限 | 2026年6月18日（期限内に連絡なければ公開） |
| Kodak の認定 | 一部データへの「一時的な不正アクセス」を確認 |
| 業務影響 | なし（Kodak 公式発表） |

### ShinyHunters の手口

ShinyHunters（Mandiant は UNC6240 として追跡）は今年に入り複数の大規模侵害を実行している：

- Oracle PeopleSoft（CVE-2026-35273）による大学100社超への侵入
- Canvas LMS（Instructure）から2億7500万件の学生データ窃取
- 今回の Kodak

今回の Kodak 侵害では、侵害経路の技術的詳細は不明。ShinyHunters はデータのサンプルや証拠ファイルを一切公開しておらず、220万件という主張の正確性は独立検証されていない。

### 対応状況

Kodak は以下の対応を表明：
- 外部サイバーセキュリティ専門家と契約して調査中
- 法執行機関に報告済み
- アクセスされ複製されたデータの特定作業を継続

### 注意点と評価

ShinyHunters は過去に主張を誇張することがあり、今回も220万件の証拠提示がない。ただし Kodak が不正アクセス自体は認めているため、何らかの侵害が発生したことは事実。被害規模の確定には引き続き調査が必要。

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) — 同一脅威アクター ShinyHunters による連続侵害キャンペーン
- [ShinyHunters、Canvas LMS（Instructure）を二度侵害：2億7500万件の学生・教職員データを要求](../articles/2026-06-16-shinyhunters-canvas-lms-breach.md) — 同一脅威アクターによる教育機関への大規模攻撃
