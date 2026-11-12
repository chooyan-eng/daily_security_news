# Microsoft 2026年11月の月例更新、過去最大級の1,000件超を修正 Outlookゼロデイ CVE-2026-124194 が悪用済み

- **日付**: 2026-11-12
- **出典**: [Qualys](https://blog.qualys.com/vulnerabilities-threat-research/2026/11/10/microsoft-patch-tuesday-november-2026-security-update-review)
- **トピック**: [Microsoft Patch Tuesday 2026年11月](../topics/microsoft-patch-tuesday-november-2026.md)
- **分類**: 新規

## 概要

Microsoft は11月10日（米国時間）に月例セキュリティ更新を公開し、1,000件を超えるCVE（報道により1,093〜1,259件）を修正した。Critical は63件。Outlook のスプーフィング脆弱性 CVE-2026-124194（CVSS 6.5）は悪用が確認済みで、NTLMv2 ハッシュ漏えいにつながる。CISA は KEV に追加し期限を11月24日とした。

## 詳細

### 悪用が確認された脆弱性

**CVE-2026-124194（Microsoft Outlook スプーフィング、CVSS 6.5、Moderate）**

- 細工されたメッセージファイルをユーザーが開くと、ユーザーの **NTLMv2 認証情報（ハッシュ）が攻撃者に漏えい**する。
- Microsoft は「悪用あり・一般公開なし」としている。プレビューウィンドウは攻撃経路ではなく、被害者がファイルを能動的に開く必要がある。
- 修正は Microsoft 365 Apps／Office LTSC の更新で提供される。
- CISA は11月10日に KEV カタログへ追加。連邦機関の対応期限は11月24日。

### 主な Critical 脆弱性（いずれも悪用未確認）

| CVE | 対象 | 内容 |
|-----|------|------|
| CVE-2026-119958 | Windows LDAP | 未認証でのリモートコード実行（CVSS 9.8） |
| CVE-2026-116928 | Windows Search（一部報道では Exchange 関連と記載） | RCE（CVSS 9.8） |
| CVE-2026-120002 | SharePoint Server | CVSS 9.9、今月最高スコアの一つ。SharePoint 関連は27件 |
| CVE-2026-118207 | Exchange Server | 認証済み攻撃者によるRCE（CVSS 8.8、入力検証不備） |

### 件数について

修正総数は情報源により 1,093／1,094／1,235／1,259 件と幅がある（Chromium 由来や事前公開分、サードパーティ分の数え方の違いとみられる）。Windows 単体で726件との集計もある。いずれにせよ単月として過去最大規模で、AI支援による脆弱性発見の増加が背景にあるとの指摘が複数の解説で見られる。正確な数値は Microsoft Security Update Guide を参照のこと。

### 技術的な補足（Web・アプリ運用者向け）

- CVE-2026-124194 は NTLM リレー／オフラインクラックに悪用される典型的な「強制認証」型。パッチ適用に加え、**外向き SMB（TCP 445）および WebDAV の遮断**、NTLM の制限・監査、Protected Users グループの活用、SMB 署名／EPA の有効化が緩和策となる。漏えいしたハッシュは社内Webアプリ（IIS 統合 Windows 認証、ADFS、Exchange 等）へのリレーに使われうる。
- SharePoint／Exchange のオンプレミス環境は過去にもパッチ公開後短期間で悪用が始まっており、インターネット公開しているサーバーは優先的に適用したい。
- LDAP の未認証 RCE はドメインコントローラーが対象となるため、DC の更新を最優先とし、LDAP／LDAPS を信頼できないネットワークに露出させないこと。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

