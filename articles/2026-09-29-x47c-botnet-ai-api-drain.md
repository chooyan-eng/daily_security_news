# Windowsボットネット「x47.c」、被害者のAI APIクレジットを浪費させる「AI API drain」機能を提供

- **日付**: 2026-09-29
- **出典**: [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/x47c-botnet-ai-api-draining-18/)
- **トピック**: [Windowsボットネット「x47.c」AI API枯渇（denial of wallet）攻撃（2026年）](../topics/x47c-botnet-ai-api-drain-2026.md)
- **分類**: 新規

## 概要

未報告だったWindowsボットネット「x47.c」が、18種の攻撃手法の一つとして、AI APIの課金枠を消尽させる「AI API drain」を提供していることが報じられた。販売者はWraithToolsで、フルパッケージは950ドル。AI機能を持つWebアプリの運用コストを狙う攻撃である。

## 詳細

- 販売者「WraithTools」が提供。フルパッケージ（約950ドル）にはDDoS機能、認証情報窃取、SOCKS5プロキシ、感染維持のためのAIモジュールが含まれる。
- 「AI API drain」は、有効なOpenAI・xAI等互換チャットAPIのキーを取り込み、プロバイダーへ直接課金リクエストを繰り返し送信する。リクエストは被害アプリを経由しないため、サイトが稼働したままAI機能の利用枠だけが尽きる（denial of wallet）。
- 標的として、チャットボット、AI連携CMS、取引ボット、スキャナなどが想定され、競合への攻撃代行としても売り込まれている。
- 他の手法はHTTPフラッド、Slow HTTP、TCP/UDPフラッド、TLS負荷、リフレクション/増幅など。

**技術的観点の補足**
- AI機能を組み込むWeb/モバイルアプリでは、APIキーの漏えい防止（サーバ側保持・定期ローテーション）、利用量上限・アラート設定、レート制限が有効。

---

## 関連記事
