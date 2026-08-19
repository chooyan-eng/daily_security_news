# CISA、Joomla の iCagenda・Balbooa Forms 拡張機能のゼロデイ悪用をKEVカタログに追加

- **日付**: 2026-07-14
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/icagenda-and-balbooa-forms-joomla-flaws.html)
- **トピック**: [Joomla iCagenda / Balbooa Forms 拡張機能 ゼロデイ RCE（2026年6-7月）](../topics/joomla-icagenda-balbooa-zero-day-2026.md)
- **分類**: 新規

## 概要

Joomla 用イベント管理拡張機能「iCagenda」とフォーム作成拡張機能「Balbooa Forms」に存在する、いずれもCVSS 10.0の任意ファイルアップロード脆弱性が、CVE採番前からゼロデイとして実際に悪用されていたことが判明した。CISAは両脆弱性をKnown Exploited Vulnerabilities（KEV）カタログに追加し、連邦政府機関に2026年7月13日までの修正を義務付けた。

## 詳細

### 脆弱性の詳細

**CVE-2026-48939（iCagenda）**
ファイル添付機能を通じて任意のファイルをアップロードできる脆弱性で、最終的にPHPコードのアップロード・実行につながる。mySites.guru の分析によれば、CVE採番前の2026年6月15日から、iCagendaを導入しているJoomlaサイトを狙った自動化攻撃でゼロデイとして悪用されていた。開発元のJoomliCは、バージョン4.0.8および3.9.15で修正版を公開済み。

**CVE-2026-56291（Balbooa Forms）**
同じく任意ファイルアップロードからリモートコード実行（RCE）に至る脆弱性。2026年7月8日、mySites.guruの顧客環境で発生した実際の攻撃を通じて発見された。バージョン2.4.1で修正済み。

### CISAの対応

CISAは両CVEをKEVカタログに追加し、連邦文民行政機関（FCEB）に対し2026年7月13日までの是正を義務付けた。CVE-2026-48939については既にKEVに追加済みのAdobe ColdFusion（CVE-2026-48282、CVSS 10.0）やJoomlack Page Builder CK（CVE-2026-56290、CVSS 10.0）と合わせ、2026年7月に入りWebコンテンツ管理システム関連の最大深刻度脆弱性の実悪用が相次いで確認されている。

### 技術的補足

いずれの脆弱性も「認証不要のファイルアップロード機能」という共通の弱点を突いており、CMS拡張機能におけるファイルアップロード処理の検証不備が繰り返し攻撃の入口となっている実態を示す。CVE番号が正式に採番される前から自動化スキャンによる無差別攻撃が展開されていた点は、パッチ公開までの「ゼロデイ悪用ウィンドウ」がWebサイト運営者にとって現実的なリスクであることを裏付けている。

---

## 関連記事

なし（新規トピック）
