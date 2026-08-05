# Adobe Campaign Classicに最大深刻度（CVSS 10.0）の脆弱性3件、未認証でのコード実行が可能に

- **日付**: 2026-08-03
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/adobe-campaign-classic-cvss-100-flaw.html)
- **出典**: [SecurityAffairs](https://securityaffairs.com/196429/security/adobe-fixed-a-maximum-severity-vulnerability-flaw-in-campaign-classic.html)
- **トピック**: [Adobe Campaign Classic 重大脆弱性（2026年8月）](../topics/adobe-campaign-classic-vulnerabilities-2026.md)
- **分類**: 新規

## 概要

Adobeはマーケティングオートメーション製品「Campaign Classic（ACC）」に対し、最優先度（Priority 1）のセキュリティアップデート「APSB26-120」を公開した。CVE-2026-48331（SSRF）、CVE-2026-48323（テンプレートエンジンインジェクション）、CVE-2026-48330（SQLインジェクション）の3件はいずれもCVSS 10.0の未認証・リモートから任意コード実行につながる脆弱性で、外部公開されたACC環境の早急なパッチ適用が求められている。

## 詳細

2026年8月3日公開のセキュリティ情報APSB26-120では、WindowsおよびLinux上のAdobe Campaign Classic v7.4.3ビルド9398以前が影響を受けるとされ、修正版のv7.4.3ビルド9399へのアップグレードが推奨されている。

最も深刻な3件はいずれもCVSS 10.0満点で、未認証のリモート攻撃者による任意コード実行を許す可能性がある。

- **CVE-2026-48331**：サーバーサイドリクエストフォージェリ（SSRF）
- **CVE-2026-48323**：テンプレートエンジンインジェクション
- **CVE-2026-48330**：SQLインジェクション

Adobeは本記事作成時点で、これらの脆弱性が実際に悪用された事例は確認していないとしている。ただし、インターネットに公開されたCampaign Classic環境は特にリスクが高く、セキュリティチームには管理画面・アプリケーションインターフェースへの外部アクセス制限、Webおよびアプリケーションログの不審なリクエストの精査、Campaignサーバーからの予期しない外向き通信の調査が推奨されている。

### 影響範囲

- 製品：Adobe Campaign Classic（ACC）v7.4.3 build 9398以前
- 修正版：v7.4.3 build 9399
- 脆弱性：CVE-2026-48331（SSRF）、CVE-2026-48323（テンプレートインジェクション）、CVE-2026-48330（SQLi）　いずれもCVSS 10.0
- 悪用状況：本記事作成時点で確認事例なし（Adobe公表）

### セキュリティ上の考察

マーケティングオートメーション製品は顧客データベースと直結し、外部公開されるWebインターフェースを持つことが多いため、SSRF・SQLi・テンプレートインジェクションといった複数の未認証RCEクラス脆弱性が同時に存在する今回のケースは高リスクである。悪用実績が未確認の今のうちにパッチ適用と外部露出の見直しを行うことが重要となる。

---

## 関連記事

なし（新規トピック）
