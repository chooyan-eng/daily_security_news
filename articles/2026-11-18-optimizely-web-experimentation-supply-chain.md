# Optimizelyのサインアップ処理の脆弱性を悪用、178組織のWebサイトに悪性JavaScript CNN・BBC・SalesforceなどでカードスキマーやiOSエクスプロイトを配信

- **日付**: 2026-11-18
- **出典**: [Report URI](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/), [Krebs on Security](https://krebsonsecurity.com/2026/11/attackers-used-optimizely-to-a-b-test-malware-on-top-websites/), [The Record](https://therecord.media/optimizely-malicious-code-customer-sites), [BleepingComputer](https://www.bleepingcomputer.com/news/security/optimizely-supply-chain-attack-delivers-malware-to-cnn-fox-news-bbc-salesforce-sites/)
- **トピック**: [Optimizely Web Experimentation 侵害によるWebサプライチェーン攻撃（2026年11月）](../topics/optimizely-web-experimentation-supply-chain-2026.md)
- **分類**: 新規

## 概要

A/Bテスト基盤Optimizely Web Experimentationのアカウントサインアップ処理の脆弱性が11月16日に悪用され、少なくとも178組織の顧客プロジェクトに悪性JavaScriptが注入された。暗号資産アドレスの差し替え、カードスキミング、Cookie窃取に加え、iPhone/iPad向けにエクスプロイトキットCoruna・DarkSwordが配信された。

## 詳細

### 概要

Report URIのScott Helme氏が11月16日に発見・公表した。Optimizelyによれば、攻撃者はWeb Experimentationのアカウントサインアップ処理の弱点を突き、パスワードを盗むことなく顧客の管理者になりすまし、各プロジェクトの「Project JavaScript」を改ざんした。Optimizelyのスニペットは顧客サイトの全ページに読み込まれるため、改ざんされたコードがそのまま訪問者のブラウザで実行された。

### 影響範囲

- Helme氏らが調査した1,611個のスニペットのうち188個が汚染されており、178組織に対応。Zoom、BBC、CNN、Fox News、Salesforce、GitLabなどの名前が挙がっている。調査できたのは一部のスクリプトのみで、実数はより多い可能性がある。
- 悪性スクリプトは11月16日に約17時間配信されたとする報道がある。
- 同じコードは9月にトルコのサイトで先行して観測されていたという。

### ペイロード

- 暗号資産ウォレットアドレスの差し替え（クリッパー）
- 決済カード情報のスキミング
- Cookie・スクリーンショットの窃取
- iPhone/iPadでは、OSバージョンに応じて隠し要素経由でエクスプロイトキットCorunaまたはDarkSwordを配信（Krebs on Securityは、複数の脆弱性を連鎖させるゼロクリック型キットと説明）

Helme氏が追跡した攻撃者ウォレットへの流入は約7,000ドル相当。カードスキミングによる被害規模は不明。

### Optimizelyの対応

同社は同日中に活動を検知し、悪性コードの配信を遮断、検知から3時間以内に脆弱性を修正したとしている。「当社システムに悪性コードは残っていない」と述べる一方、ステータスページ上は未解決表示が続いていると報じられた。全サイトが完全に修復されたか、攻撃者がアクセスを保持していないかは明確でない。

### 技術的な補足

- CSP（Content Security Policy）でOptimizelyのドメインを許可していても防げない。悪性コードが正規ドメインから配信されるためである。Helme氏もこの点を指摘している。
- 顧客ごとに内容が動的に変わるタグ管理・A/Bテスト系スクリプトはSRI（Subresource Integrity）を適用しにくく、第三者スクリプトの完全性検証が構造的に難しい。決済・ログインなど機微なページでは第三者スクリプトを読み込まない、connect-src等で送信先を絞る、CSPレポートで未知の通信先を監視する、といった多層の対策が現実的となる。
- Optimizely利用組織は、Project JavaScriptやカスタムコードの変更履歴、コラボレーター一覧、APIトークンを確認し、11月16日前後の不審な変更を洗い出すべきである。
- 利用者側は、該当時間帯に対象サイトで決済した場合のカード明細確認、iOS/iPadOSの最新版への更新が推奨される。

iOS向けエクスプロイトを正規サイト経由で配る点は、11月上旬に報告されたMidnight Blizzardの水飲み場攻撃（[関連記事](./2026-11-05-midnight-blizzard-mobile-watering-hole.md)）と手口が似るが、両者の関連を示す情報はない。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事
