# CISA、Mitel MiCollabの5件を含む実悪用脆弱性10件をKEVに追加

- **日付**: 2026-11-27
- **出典**: [Cyber Security News](https://cybersecuritynews.com/cisa-adds-10-flaws-to-kev/)
- **トピック**: [CISA KEV 2026年11月25日追加（Mitel MiCollab 5件ほか計10件）](../topics/cisa-kev-2026-11-25-mitel-micollab.md)
- **分類**: 新規

## 概要

CISAは11月25日、Mitel MiCollabの5件のほか、Danfoss、HPE、Juniper、Vates Xen Orchestraの脆弱性を含む計10件をKEVカタログに追加した。MiCollabの CVE-2026-133311 は弱い認証の問題で、修正版は10.3.0.18。

## 詳細

### 追加内容

11月25日付でKEVに10件が追加され、うち5件がMitel MiCollab（ユニファイドコミュニケーション製品。Web・モバイルクライアントを持つ）に関するもの。代表的な CVE-2026-133311 は弱い認証（weak authentication）に分類される。Mitelのアドバイザリは MISA-2026-0012。その他、Danfoss、HPE、Juniper、Vates Xen Orchestra の脆弱性が含まれる。

- 是正期限: 大半は11月28日、CVE-2026-133311 は12月9日と報じられている。
- CVSSは情報源により食い違い（CVE-2026-133311 について5.9とする情報と9.5とする情報）があり、NVD／ベンダーアドバイザリでの確認が必要。

### 直前の追加: Optimizely

11月24日には Optimizely Web Experimentation の CVE-2026-132224（重要な状態データの外部制御）もKEV入りしている。サインアップ処理の不備により攻撃者が同サービスのユーザーになりすまし、プロジェクトのJavaScriptを注入できたもので、Optimizelyは11月16日に悪用されたと説明。A/Bテスト用スニペットを読み込む多数のサイト訪問者に悪性スクリプトが配信されたと報じられている。サードパーティJSを読み込むWebサイト運営者は、SRIが使えない動的スニペットのリスクとCSPによる緩和を再点検したい。

### 対処

- MiCollab: 10.3（10.3.0.18）へ更新。即時適用が難しい場合は Audio, Web and Video Conferencing コンポーネントへの外部アクセスを制限。
- Xen Orchestra、Juniper、HPE、Danfoss 各製品: ベンダーアドバイザリに従い更新し、管理インターフェースをインターネットに露出させない。

参考: [The Terminal](https://theterminal.space/security/cisa-kev-nov-25-mitel-xen-orchestra-juniper-danfoss)、[Brandefense（CVE-2026-132224）](https://brandefense.io/knowledge-hub/vulnerabilities/cve-2026-132224/)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

