# Optimizely経由のサプライチェーン攻撃「OPTIMJACK」、178組織のサイトに悪性JavaScript——カードスキマー・暗号資産クリッパー・iOSエクスプロイトを配信

- **日付**: 2026-11-20
- **出典**: [Dark Reading](https://www.darkreading.com/cyber-risk/optimizely-malware-attacks-third-party-vendor-risks)
- **トピック**: [Optimizely「OPTIMJACK」サプライチェーン攻撃（2026年11月）](../topics/optimizely-optimjack-supply-chain-2026.md)
- **分類**: 新規

## 概要

A/Bテスト基盤Optimizely Web Experimentationの脆弱性が悪用され、11月16日に顧客プロジェクトへ悪性JavaScriptが注入された。Report URIの調査では1,611スニペット中188件（178組織）が汚染され、BBC、CNN、Zoom、HSBC、IKEAなどが含まれる。ペイロードは暗号資産アドレスのすり替え、カード情報のスキミング、iOS向けエクスプロイトキット（Coruna/DarkSword）の配信を行う。サードパーティスクリプトのリスクを改めて示す事案として分析が続いている。

## 詳細

### 事案の概要

- **発生**: 2026-11-16、Optimizely Web Experimentationの顧客プロジェクトに悪性JavaScriptが注入された。
- **確認**: 2026-11-17、Optimizelyが事案を認め、脆弱性の修正、注入コードの除去、影響アカウントの保護、不正なコード配信に対する追加防御の導入を発表。顧客データへの不正アクセスが確認された場合は遅滞なく通知するとしている。
- **発見者**: Report URIのScott Helme氏。
- **通称**: OPTIMJACK（StepSecurity等）。

### 規模

- Report URIが調査した1,611件のOptimizelyスニペットのうち188件が汚染、178組織に相当。調査時点で取得できたスニペットのみの集計であり、178は下限値。
- 悪性コードが配信されたページ訪問は約3,400万回（推定幅600万〜1.5億回）。
- 名前が挙がっている組織: Zoom、BBC、CNN、Salesforce、GitLab、HSBC、IKEA、Ledger など。RH-ISACは小売・旅行業界への影響を警告。

### 原因

- Optimizelyの説明では、Experimentation製品の**新規アカウント作成（サインアップ）フローの不具合**が原因。これにより無関係な顧客プロジェクトへの書き込みが可能になった仕組みの詳細や修正内容は公表されていない。
- 悪性コードはプロジェクト設定の「Project JavaScript」フィールドに追加されたと報じられている。
- CVEについては情報が割れており、CVE-2026-132224とする記事と、CVE未採番とする記事がある。

### ペイロードの挙動

- **暗号資産クリッパー**: クリップボード/ページ上のウォレットアドレスを攻撃者のものにすり替え。
- **カードスキマー**: 決済フォームからカード番号等を窃取（Magecart型）。
- **Cookie・スクリーンショットの窃取**。
- **iOS/iPadOS向けエクスプロイトキットの配信**: iOS 13〜17にはCoruna、iOS 18にはDarkSwordをバージョン判定のうえロード。実際に端末侵害が成立した範囲は不明。

### なぜ防げなかったか（技術的な補足）

- スニペットはプロジェクトごとに生成され、`cdn.optimizely.com` からOptimizelyの正規TLS証明書で配信される。そのため、**CSPやファイアウォールで当該CDNを許可していたサイトでは、その許可設定自体が配信経路になった**。
- A/Bテストのスニペットは内容が頻繁に変わる前提のため、Subresource Integrity（SRI）によるハッシュ固定が事実上適用できない。これはタグマネージャーや解析タグ全般に共通する構造的な弱点。
- 対策として挙げられるもの: (1) 決済・ログインなど機微なページからサードパーティスクリプトを排除する、(2) スクリプトの自社ホスティング/プロキシとレビュー付きデプロイ、(3) CSPの `connect-src`/`form-action` 等による送信先の制限とレポート監視、(4) スクリプト内容の変更検知、(5) PCI DSS v4.0.1 要件6.4.3/11.6.1に沿った決済ページのスクリプト管理。
- 影響サイトの運用者は、11月16日前後のスニペット内容・CSPレポート・決済ページのアクセスログを確認し、スキミングの可能性がある場合はカード会社・利用者への通知を検討する必要がある。

### 関連する過去事案

11月上旬にはロシア系APT29（Midnight Blizzard）が改ざんサイトと解析スクリプトの乗っ取りによりiOS/Android向けn-dayチェーンを配信した水飲み場攻撃が報告されており、「信頼されたサードパーティスクリプト経由でモバイル端末を狙う」手口が続いている（攻撃者の関連性は示されていない）。

### 参考

- [Help Net Security: Malware spread through Optimizely hits 178 organizations](https://www.helpnetsecurity.com/2026/11/17/optimizely-vulnerability-malicious-javascript/)
- [StepSecurity: OPTIMJACK](https://www.stepsecurity.io/blog/optimjack-optimizely-hosted-scripts-crypto-clipper-card-skimmer)
- [SecurityWeek: Optimizely Vulnerability Exploited to Serve Malware on Major Websites](https://www.securityweek.com/optimizely-vulnerability-exploited-to-serve-malware-on-major-websites/)
- [MacRumors: iPhone Users Targeted in Major Website Security Breach](https://www.macrumors.com/2026/11/17/iphone-users-targeted-website-security-breach/)
- [RH-ISAC](https://rhisac.org/general-blog/campaign-compromises-optimizely-platform-to-distribute-malicious-javascript-to-target-retail-travel-entities/)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

