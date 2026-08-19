# FortiSandbox 続報：CISA が CVE-2026-39808／CVE-2026-25089 を KEV に追加、連邦機関に7月19日までの対応を要求

- **日付**: 2026-07-18
- **出典**: [The Register](https://www.theregister.com/security/2026/07/17/attackers-target-critical-fortisandbox-flaws-as-cisa-issues-patch-order/5274287)
- **トピック**: [Fortinet FortiSandbox 脆弱性の積極的悪用（2026年6月）](../topics/fortinet-fortisandbox-cve-2026.md)
- **分類**: 続報

## 概要

CISAは2026年7月16日、Fortinet FortiSandbox のOSコマンドインジェクション脆弱性 CVE-2026-39808・CVE-2026-25089（CVSS 9.1）をKnown Exploited Vulnerabilities（KEV）カタログに正式追加した。両脆弱性は既存トピックで6月から追跡している悪用キャンペーンの対象そのものであり、悪用が継続していることを裏付ける公式な続報となる。連邦機関は2026年7月19日までの対応が義務付けられた。

## 詳細

### KEV追加の内容

CISAは CVE-2026-39808 と CVE-2026-25089 の2件を KEV カタログに追加した。両脆弱性は特別に細工した HTTP リクエストを通じて、認証情報なしで任意のOSコマンドを実行できる OS コマンドインジェクション（CWE-78）に分類される。CVE-2026-25089 は FortiSandbox 本体に加え、FortiSandbox Cloud・FortiSandbox PaaS 環境にも影響する点で影響範囲が広い。

### 既存キャンペーンとの関係

これらのCVEは、既存トピックで追跡している「FortiSandbox 3件の重大脆弱性の積極的悪用」（CVE-2026-39813・CVE-2026-39808・CVE-2026-25089）の一部であり、2026年4月のパッチ提供・6月中旬以降の悪用観測に続く公式な確認となる。CISAによるKEV追加は、民間セキュリティベンダーが報告していた悪用実態を連邦政府として正式に裏付けたものである。

### 対応期限と重要性

BOD 26-04 に基づき、連邦民間行政機関（FCEB）は2026年7月19日までにベンダー提供の緩和策を実施する義務を負う。FortiSandbox の企業導入数自体は限定的だが、金融サービス・大企業・重要インフラなど高価値セクターでの採用が多く、侵害時の影響が大きいと評価されている。

### 推奨対応

- FortiSandbox・FortiSandbox Cloud・FortiSandbox PaaS を利用する組織は、Fortinet提供のパッチを直ちに適用する
- インターネットからの直接アクセスを制限する
- 6月中旬以降に観測された攻撃元IP（141.11.43.175 等）からの通信をログで確認する

---

## 関連記事

なし（既存トピックへの続報のため）
