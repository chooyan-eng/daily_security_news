# Atlas Elektronik — TheGentlemen ランサムウェアが欧州防衛技術企業を侵害

- **日付**: 2026-06-29
- **出典**: [Breachsense](https://www.breachsense.com/breaches/) / [Halcyon TheGentlemen Analysis](https://www.halcyon.ai/ransomware-research-reports/threat-assessment-the-gentlemen-ransomware-group) / [SecurityArsenal](https://securityarsenal.com/blog/thegentlemen-ransomware-critical-surge-in-manufacturing-and-energy-sectors-leveraging-perimeter-exploits)
- **トピック**: [TheGentlemen ランサムウェアグループ（2026年）](../topics/thegentlemen-ransomware-2026.md)
- **分類**: 新規

## 概要

欧州を代表する防衛技術企業 Atlas Elektronik GmbH（ドイツ）が、急成長中のランサムウェアグループ「TheGentlemen」による侵害を受けたことが6月26日に判明した。TheGentlemen は2025年中旬に登場した比較的新興のグループだが、2026年だけで240件以上の被害を記録する急拡大を続けており、製造・エネルギーセクターへの攻撃に特化している。

## 詳細

### Atlas Elektronik について

Atlas Elektronik GmbH はドイツの防衛技術企業で、海軍システム・機雷対策・水中探知機器・艦艇制御システムなどの開発・製造を手掛けている。TKMS（ThyssenKrupp Marine Systems）とDIEHL Defenceの合弁会社として設立されており、NATO各国の海軍に納入実績を持つ。

防衛産業企業としての性格上、侵害によって流出する可能性のあるデータには知的財産（設計図・仕様書）、政府との契約情報、機密性の高い技術文書が含まれる。

### TheGentlemen ランサムウェアグループ

TheGentlemen は2025年中旬に活動を開始した比較的新興のランサムウェアアズアサービス（RaaS）グループで、被害者数の増加速度は記録上最速クラスとされる：

- **設立以来の被害者公表数**: 332件以上
- **2026年の被害者数**: 240件以上
- **2026年の活動ランキング**: 被害者数ベースで第2位

### 攻撃手法

TheGentlemen の特徴的な攻撃手法は**ペリメーターデバイスの脆弱性悪用**に依存する：

- **Check Point・Cisco ファイアウォールの CVE を積極的に武器化**してVPN認証をバイパス
- **ConnectWise ScreenConnect の既知エクスプロイト**を活用してRMM（リモート管理ツール）を掌握
- 伝統的なフィッシングよりも、インターネット公開機器の脆弱性を優先的に利用

**ダブルエクスポージョンモデル**を採用：
1. 暗号化前に機密データを窃取（CADデザイン・知的財産・従業員記録等）
2. 身代金要求（被害者の収益規模に応じて $500k〜$5M）
3. 支払いなければデータ公開

### 6月26日の複数被害

Atlas Elektronik 以外に、同日(6月26日)に以下の組織もTheGentlemen等の各種グループによる被害が確認された：

| 組織 | 業種 | 脅威アクター |
|------|------|------------|
| MagMutual Insurance | 保険 | LeakNet |
| Nachlass Nord | 遺産管理（ドイツ） | ANUBIS |
| 911 Driving School | 教育（米国） | PrinzEugen |
| Clearview Eye Centre | 眼科 | Interlock |
| Frosty Acres Brands | 食品サービス | Booba |

### 産業・防衛セクターへのリスク

TheGentlemen が製造・エネルギー・防衛セクターに注力している背景：

1. これらのセクターは操業停止に対する耐性が低く、身代金支払いへの圧力が高い
2. 機密性の高い知的財産を大量に保有しており、データ漏洩の脅迫効果が高い
3. セキュリティ投資が IT 中心企業と比較して遅れているケースがある
4. 国家安全保障上の重要性から、当局による調査も激化する

---

## 関連記事

なし（新規トピック）
