# DHS、情報共有プラットフォーム「HSIN」への不正侵入を確認 — SharePoint環境も標的に

- **日付**: 2026-07-07
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/dhs-confirms-hackers-breached-hsin-info-sharing-platform/), [UpGuard](https://www.upguard.com/news/department-of-homeland-security-data-breach-2026-07-01), [Nextgov/FCW](https://www.nextgov.com/cybersecurity/2026/06/hackers-breached-dhs-information-sharing-network-people-familiar-say/414534/)
- **トピック**: [Microsoft SharePoint Server CVE-2026-45659 リモートコード実行脆弱性](../topics/sharepoint-cve-2026-45659-rce.md)
- **分類**: 関連

## 概要

米国土安全保障省（DHS）は、連邦・州・地方・民間パートナーが利用する情報共有プラットフォーム「Homeland Security Information Network（HSIN）」への不正侵入を確認したと発表。侵入は2026年5月末〜6月初旬の間に発生したとみられ、HSINサーバーに加え、部局間連携用のSharePoint環境も標的となった。侵害範囲や具体的な攻撃手法は調査中。

## 詳細

DHSは、連邦・州・地方・部族・準州・国際機関・民間セクターのパートナーが脅威情報の共有やインシデント対応の調整に利用する「Homeland Security Information Network（HSIN）」に、身元不明の脅威アクターによる不正アクセスがあったことを確認した。侵入は2026年5月末から6月初旬の間に発生したとみられているが、報道で最初に取り上げられたのは2026年7月1日である。

侵入の対象となったのは、HSINのサーバー群に加え、複数機関の連携作業に利用されているSharePoint環境であることが判明している。両システムが並行して侵害された事実は、日和見的な脆弱性悪用というよりも、特権的な足がかりを得た標的型侵入である可能性を示唆している。単一の認証情報漏洩、OAuthトークン窃取、あるいはサーバーサイドの脆弱性悪用のいずれかが、HSINのネットワーク公開サーバーとSharePoint環境の双方への横断的アクセスを可能にした経路として考えられる。

なお、DHSは本侵入を特定の脅威アクターや国家に帰属させておらず、機密システム（classified systems）への影響はないとしている。プラットフォーム自体はパートナー向けに稼働を継続しており、文書が実際に持ち出されたかどうかも現時点では明らかにされていない。

注目すべき点として、CISAがSharePoint Serverの信頼できないデータのデシリアライゼーションに起因するRCE脆弱性CVE-2026-45659をKEV（Known Exploited Vulnerabilities）カタログに追加した日付（2026年7月1日）が、DHSが本侵入を報道機関に確認した日と同日であった。もっとも、公開されている情報の範囲では、HSIN侵入の具体的な侵入経路がCVE-2026-45659と直接結びつくとは確認されていない。米国では現在World Cupの開催に伴う治安・警備体制の調整が進められており、Nextgovなどはこの侵害がセキュリティ計画・省庁間連携・対応手順に関する情報の露出につながった可能性を懸念している。

---

## 関連記事

- [SharePoint Server の RCE 脆弱性（CVE-2026-45659）、実悪用確認によりCISA KEVに追加](../articles/2026-07-07-sharepoint-cve-2026-45659-kev.md) - 同時期にSharePoint RCE脆弱性がKEV追加、標的の一部がSharePoint環境である点が共通（直接的な因果関係は未確認）
