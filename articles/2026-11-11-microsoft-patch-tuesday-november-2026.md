# Microsoft 2026年11月の月例更新、1,000件超を修正 Outlookのゼロデイ CVE-2026-124194 が悪用

- **日付**: 2026-11-11
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-november-2026-patch-tuesday-fixes-1-235-flaws-outlook-zero-day/)
- **トピック**: [Microsoft Patch Tuesday 2026年11月](../topics/microsoft-patch-tuesday-november-2026.md)
- **分類**: 新規

## 概要

Microsoftは11月10日、月例セキュリティ更新を公開した。修正件数は集計方法により1,093〜1,235件と報じられ、実悪用が確認されたOutlookのなりすまし脆弱性CVE-2026-124194（NTLMv2ハッシュ漏えい）を含む。SharePointやExchange Serverの重大な脆弱性も修正された。

## 詳細

**全体像**

- 公開日: 2026年11月10日
- 修正件数: 報道により1,093件（Dark Reading、Redmondmag等）、1,094件（SOCRadar等）、1,235件（BleepingComputer等）と幅がある。集計対象（Edge/Chromium、サードパーティ、月中に公開済みの修正等を含めるか）の違いとみられる
- Critical: 63〜66件（うちRCE 48件との報道）

**実悪用ゼロデイ: CVE-2026-124194（Microsoft Outlook）**

- 種別: なりすまし（Spoofing）、深刻度Moderate、CVSS 6.5
- 細工されたメッセージファイルを開かせると、Outlookが通常表示する外部コンテンツの警告なしに攻撃者管理下の場所へ接続し、ユーザーのNTLMv2認証ハッシュが漏えいする
- 漏えいしたハッシュはオフラインでの解読や、NTLMリレー攻撃による他サービスへのなりすまし認証に利用され得る

**Web系サーバー製品の注目点**

- CVE-2026-120002: SharePoint Server Subscription Editionの権限昇格（認可チェックの不備）、Critical
- CVE-2026-118207: Exchange Server Subscription Editionのリモートコード実行（入力検証不備）。深刻度の評価は報道によりHigh／Criticalで分かれる
- OutlookのCritical RCEとしてCVE-2026-111309、CVE-2026-110068、CVE-2026-110043が挙げられている

**技術的な補足**

- NTLMハッシュ漏えい型の脆弱性は深刻度スコアが低めに付く一方、実攻撃での利用頻度が高い。パッチ適用に加え、外向きSMB（TCP 445）の遮断、NTLMの制限・無効化、高権限アカウントのProtected Usersグループ登録が有効な緩和策となる。
- SharePoint／Exchangeのオンプレミス版は過去に公開直後の悪用が繰り返されているため、インターネットに公開している場合は優先して適用したい。
- CVE-2026-124194の詳細は確認できた情報源が限られるため、Microsoft Security Update Guideでの確認を推奨する。

> 注: 本セッションでは外部サイトの本文取得ができず（ネットワーク許可外）、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

