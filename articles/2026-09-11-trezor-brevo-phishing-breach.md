# Trezor、メール配信基盤Brevoが侵害されフィッシング拡散 34.7万件のメールアドレスに影響

- **日付**: 2026-09-11
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/trezor-347-000-users-targeted-in-phishing-attacks-after-brevo-breach/), [TechCrunch](https://techcrunch.com/2026/09/11/scammers-target-hundreds-of-thousands-of-crypto-owners-after-trezor-confirms-data-breach-of-email-provider/), [Trezor公式ブログ](https://trezor.io/blog/news/security-incident-at-brevo-our-third-party-email-provider)
- **トピック**: [Trezor顧客データ漏洩：物流委託先ShipMonkのMetabase脆弱性悪用（2026年8月）](../topics/trezor-shipmonk-metabase-breach-2026.md)
- **分類**: 関連

## 概要

暗号資産ハードウェアウォレットメーカーTrezorは、利用しているメール配信基盤Brevoが侵害され、Trezorのニュースレター登録者約34.7万件のメールアドレス宛にフィッシングメールが送信されたと公表した。攻撃者はBrevoの120アカウントを悪用し、偽の「重要セキュリティ警告」メールを配信していた。

## 詳細

第三者がメール配信サービスBrevoのシステムに不正アクセスし、Trezorを含む複数の顧客アカウントを悪用してメールを送信した。Trezorのオプトインニュースレター登録者データベースから約34.7万件のメールアドレスが影響を受けた。

攻撃者は「help@trezor.io」からの送信に見せかけ、件名「Critical Security Alert: STM32 Entropy Vulnerability」のフィッシングメールを配信。Trezorのコールドウォレットに搭載されているSTM32マイクロコントローラに「ハードウェア脆弱性」があり、シード情報がブルートフォース攻撃で解読される恐れがあるという偽の警告文で、悪性アプリへ誘導しウォレットのバックアップ（リカバリーフレーズ）の入力を求める内容だった。

Trezorはフィッシングドメインを検知から約20分でDNSレベルで停止させたが、それまでに約2,500人がリンクをクリックしていたことが確認されている。Brevoは暗号資産関連企業BitBox、CoinTracking、Peach Bitcoin、Blocktrainerのメール配信基盤としても利用されており、これら各社もユーザーに注意喚起を行っている。

本件は、Trezorが2026年8月に公表した物流委託先ShipMonkのMetabase脆弱性悪用によるデータ漏洩（約1.4万件の顧客データ流出）に続く、Trezorをめぐる2件目のサードパーティ経由のセキュリティインシデントとなる。ShipMonk事案とBrevo事案はいずれも異なるベンダー・異なる侵害経路によるものだが、いずれもTrezor顧客のフィッシング標的化リスクを高めている点で関連性が高い。

---

## 関連記事

- [Trezor顧客、ShipMonk漏洩データを悪用したフィッシング電話・郵便物の被害が顕在化](../articles/2026-09-08-trezor-shipmonk-phishing-calls-letters.md) - 同じくTrezor顧客を標的としたサードパーティ経由のフィッシング被害
