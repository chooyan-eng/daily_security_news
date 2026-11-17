# 「OPTIMJACK」Optimizely Web Experimentation経由で178組織のサイトに悪性JavaScript、カードスキマーやiOSエクスプロイトキットを配信

- **日付**: 2026-11-17
- **出典**: [The Hacker News](https://thehackernews.com/2026/11/hijacked-optimizely-scripts-served-card.html)
- **トピック**: [Optimizely Web Experimentation スクリプト改ざん「OPTIMJACK」（2026年11月）](../topics/optimizely-optimjack-supply-chain-2026.md)
- **分類**: 新規

## 概要

A/BテストSaaSのOptimizelyは、11月16日にWeb Experimentation製品のアカウント登録フローの脆弱性を悪用され、顧客プロジェクトに悪性JavaScriptを注入されたと公表した。CNN、BBC、Zoom、Salesforceなど178組織のサイト訪問者に、正規のcdn.optimizely.comから配信されるスニペット経由でカードスキマー、暗号資産クリッパー、iOSエクスプロイトキットが配信された。11月17日（UTC）に封じ込め済みとされる。

## 詳細

### 概要

Optimizelyによれば、権限のない第三者がExperimentationのアカウントサインアップフローに存在した脆弱性を悪用し、顧客プロジェクトへ悪性JavaScriptを注入した。攻撃者のコードは各顧客プロジェクトの「Project JavaScript」フィールドに書き込まれ、Optimizelyのスニペットを読み込む全ページで実行された。Optimizelyは脆弱性を修正し、影響プロジェクトから注入コードを除去したとしている。攻撃者がなぜ無関係な複数顧客のプロジェクトへ書き込み権限を得られたのか、根本原因の詳細は説明されていない。

StepSecurityはこのキャンペーンを「OPTIMJACK」と命名。影響は178組織（報道により「170超」）で、調査した1,611スクリプト中188に悪性コードが含まれていたとの集計もある。

### 攻撃の仕組み

- 注入されたコードはローダーで、外部ドメイン（`1688360[.]cc` の `track.js`）から追加スクリプトを取得する。
- 最終ペイロードとして、決済フォームのカードスキマー、暗号資産ウォレットアドレスを差し替えるクリッパー、iOS向けエクスプロイトキットが報告されている。
- スニペットは `cdn.optimizely.com` からベンダー自身の証明書で配信されるため、ドメイン単位の許可リストやSRIなしの読み込みでは検知・遮断できない。
- Optimizelyのドキュメントが推奨する設定には `eval` によるコード実行を許すものがあり、これによりHSBCのサイトでは悪性コードのバックアップコピーが実行されたと報じられている。

### 技術的な補足（Webアプリ開発者向け）

- 第三者タグ（A/Bテスト、タグマネージャ、分析）は、自サイトのオリジンで任意コードを実行できる「サプライチェーン上の特権コード」である。ベンダー側の管理画面・アカウント基盤が破られると、自社のコードを一切変更されずに全訪問者が影響を受ける。
- 被害を免れたのは、`script-src` と `connect-src` を厳格に絞ったCSPを設定していたサイトだったと報告されている。ローダーが外部ドメインから2段目を取得する構造のため、`connect-src` / `script-src` の許可リストで2段目が遮断された。`unsafe-eval` を許可しないことも重要である。
- 決済ページ・ログインページには第三者タグを載せない、もしくはiframe分離した決済フォームを使う（PCI DSS v4.0.1 要件6.4.3／11.6.1のスクリプト管理・改ざん検知）ことが実効的な対策となる。
- 利用企業は、11月16日前後に自サイトから `1688360[.]cc` への通信がなかったかCSPレポートやRUMのログで確認し、決済情報入力があったページについてはカード情報漏えいとしての対応要否を判断する必要がある。
- 関連報道では、同種の悪性スクリプトがOptimizely以外の4つのWebサービス経由でも確認されたとの指摘がある（infostealers.com）。

出典（その他）: [StepSecurity](https://www.stepsecurity.io/blog/optimjack-optimizely-hosted-scripts-crypto-clipper-card-skimmer)、[BleepingComputer](https://www.bleepingcomputer.com/news/security/optimizely-supply-chain-attack-delivers-malware-to-cnn-fox-news-bbc-salesforce-sites/)、[Security Affairs](https://securityaffairs.com/203289/malware/optimjack-bbc-cnn-and-zoom-among-targets-of-optimizely-script-hijacking.html)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

