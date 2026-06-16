# ShinyHunters、Canvas LMS（Instructure）を二度侵害：2億7500万件の学生・教職員データを要求

- **日付**: 2026-06-16
- **出典**: [Wikipedia - 2026 Canvas data breach](https://en.wikipedia.org/wiki/2026_Canvas_data_breach), [The Register](https://www.theregister.com/security/2026/05/12/double-canvas-intrusion-confirmed-as-shinyhunters-resets-leak-deadline/5238361), [Bitdefender](https://www.bitdefender.com/en-us/blog/hotforsecurity/fbi-shinyhunters-canvas-breach)
- **トピック**: [ShinyHunters による Oracle PeopleSoft 攻撃キャンペーン](../topics/shinyhunters-oracle-peoplesoft.md)
- **分類**: 関連

## 概要

脅威アクターShinyHuntersが2026年4月〜5月にかけて、米国最大の学習管理システム（LMS）であるCanvas（Instructure社）を二度にわたって侵害した。同社が接触した9,000以上の教育機関を通じて2億7500万件の学生・教職員データが窃取されたと主張。Instructureが「データの破棄に関する合意」に達したと発表する一方、FBIは対象学生・教職員への警告を発した。

## 詳細

### 侵害の経緯

**2026年4月25日**: ShinyHuntersが最初のCanvas侵害を実施。ユーザー名・メールアドレス・学生IDなどが窃取される。

**2026年5月6日**: Instructureが「状況は収拾した」と発表。

**2026年5月7日**: ShinyHuntersが二度目の侵害を実施し、Canvasのログインページをランサムウェアメッセージに差し替え。9,000以上の学校にまたがる2億7500万件のデータを保有すると主張し、身代金支払いを要求（期限：2026年5月12日）。

**2026年5月11日**: InstructureはShinyHuntersと「侵害データの破棄に関する合意」に達したと発表。Canvasは完全に復旧し、ShinyHuntersのリークサイトからInstructureの記載が削除された。

**2026年5月以降**: InstructureはShinyHuntersとの合意に言及しながらも、詳細は非開示。FBIは侵害を受けた学生・教職員への警告を発し、ShinyHuntersからの連絡に注意するよう呼びかけた。

### 被害の規模

- **主張されるレコード数**: 2億7500万件（ShinyHuntershによる主張）
- **対象機関数**: 9,000以上の教育機関
- **漏洩データの種類**: 氏名、メールアドレス、学生ID番号、ユーザー間のメッセージ等
- **Instructure確認の非漏洩データ**: パスワード、生年月日、政府発行ID、財務情報

### Instructure の公式対応

InstructureはFree-For-Teacherアカウントプログラムを永久閉鎖したことを発表。同プログラムは侵害の初期アクセスベクターになったと推測されている。

### ShinyHuntersの脅威アクタープロフィール（Oracle PeopleSoft攻撃との比較）

本事案は同じShinyHunters（Mandiant追跡名：UNC6240）が関与しており、この脅威グループの活動範囲の広さを改めて示している：

| 項目 | Oracle PeopleSoft攻撃 | Canvas侵害 |
|---|---|---|
| ターゲット | 大学・企業100社以上 | Instructure（9,000機関を経由） |
| 悪用手法 | ゼロデイ（CVE-2026-35273） | 非公開 |
| 攻撃時期 | 2026年5月〜6月 | 2026年4月〜5月 |
| データ規模 | 非公表 | 2億7500万件（主張） |
| 解決 | Oracle がパッチ公開 | データ破棄合意（確認不能） |

---

## 関連記事

- [ShinyHuntersがOracle PeopleSoftのゼロデイ（CVE-2026-35273）を悪用し大学等100社以上に侵入](../articles/2026-06-16-shinyhunters-oracle-peoplesoft-cve-2026-35273.md) - 同一脅威アクターによる別キャンペーン
