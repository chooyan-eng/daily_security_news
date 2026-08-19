# Polymarketフロントエンド侵害：サードパーティベンダー経由のスクリプトインジェクションで約300万ドル流出

- **日付**: 2026-06-27
- **出典**: [CyberNews](https://cybernews.com/security/polymarket-hit-by-cyberattack-via-third-party-dependency/), [The Next Web](https://thenextweb.com/news/polymarket-hack-3-million-stolen-third-party-breach), [TechRadar](https://www.techradar.com/pro/security/prediction-market-giant-polymarket-hit-by-cyberattack-with-company-confirming-user-funds-stolen-here-is-what-we-know)
- **トピック**: [Polymarket フロントエンド侵害（2026年6月）](../topics/polymarket-frontend-breach-2026.md)
- **分類**: 新規

## 概要

2026年6月25日、予測市場プラットフォームPolymarketは、サードパーティベンダーの侵害を経由して悪意あるJavaScriptコードがフロントエンドに注入され、ユーザー資産約300万ドル（pUSD）が流出したと発表した。影響を受けたユーザー数は15件未満にとどまったが、Polymarketは全額返金を約束した。

## 詳細

### 攻撃の仕組み

攻撃者はPolymarketが利用するサードパーティベンダーを侵害し、サイトのフロントエンドに悪意あるJavaScriptコードを注入した。このコードはサプライチェーン攻撃の典型的な手法で、Polymarketのコアスマートコントラクトやバックエンドシステムではなく、ユーザーインターフェース層を標的とした。

### 被害の詳細

影響を受けたユーザーがウォレットを接続すると、スクリプトはトランザクションへの署名・承認を促す偽のダイアログを表示した。対象となったのはPolymarketのプライマリステーブルコイン「pUSD」（USDCを担保とするポリゴンネットワーク上のペッグコイン）を保有するユーザー。

- 被害規模: 約294万ドル（PeckShield確認: 攻撃者は1,893 ETHをPolygonからEthereumにブリッジ後、ETHに変換）
- 影響ユーザー数: 15件未満
- 対象通貨: pUSD（Polygon上のUSDCペッグトークン）

### 攻撃者の行動

攻撃者はPolygonネットワーク上でpUSDを窃取した後、ファンドをEthereumにブリッジし、ETHに変換して攻撃者管理のウォレットに移送した。

### Polymarketの対応

- 侵害確認後、速やかに侵害を封じ込め
- 全影響ユーザーへの全額返金を確約
- 侵害されたベンダー名は非公開
- 調査中として詳細コメントを控えた

### Webアプリセキュリティへの示唆

本インシデントはサードパーティスクリプトやCDNのサプライチェーンリスクを改めて示した。フロントエンドのコンテンツセキュリティポリシー（CSP）強化、サブリソース完全性（SRI）チェック、サードパーティベンダーのセキュリティ審査が重要な対策となる。Web3プラットフォームにおいては、ウォレット接続時のトランザクション内容を注意深く確認することが不可欠。

---

## 関連記事
