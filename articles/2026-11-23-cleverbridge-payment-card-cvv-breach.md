# EC決済プラットフォームCleverbridge、攻撃者によるカード番号・有効期限・CVVのコピーを認める

- **日付**: 2026-11-23
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/11/23/cleverbridge-data-breach-card-numbers-cvv/)
- **トピック**: [Cleverbridge 決済カード情報流出事案（2026年11月）](../topics/cleverbridge-payment-card-breach-2026.md)
- **分類**: 新規

## 概要

ソフトウェア・SaaS販売向けのチェックアウト／決済代行プラットフォームを提供するCleverbridgeは、第三者が同社プラットフォーム上の決済カードデータをコピーしたと認めた。カード番号、有効期限、CVVが含まれると報じられている。不正活動の検知は11月4日、対象者への通知は11月20日開始。侵入経路と影響人数は非公表。

## 詳細

各報道によると、Cleverbridgeは11月4日に不正な活動を検知してシステムを一時停止し、11月20日から影響を受けた個人への通知を始めた。同社はランサムウェア攻撃ではないとしているが、侵入方法と対象カード数は公表していない。対象者にはCyberscoutによるクレジットモニタリングが無償提供され、カード明細の確認とカード発行会社への連絡（再発行）が推奨されている。

流出項目については報道に食い違いがある。Help Net Securityは氏名・連絡先・請求先など他の個人情報はコピーされていないと伝える一方、The Registerはメールアドレス、請求先住所、電話番号も露出した可能性があり、アカウントのパスワードは取得されていない見込みと報じている（[出典: The Register](https://www.theregister.com/cyber-crime/2026/11/23/cleverbridge-admits-attackers-stole-customers-credit-card-and-cvv-numbers-yep-you-read-that-right/5311573)、[Security Affairs](https://securityaffairs.com/203851/data-breach/cleverbridge-confirms-attackers-copied-payment-card-data-from-its-platform.html)）。

最大の未解明点はCVVである。PCI DSSはオーソリ（承認）後のCVV等の機微認証データの保存を禁じており、同社はCVVがどのように取得されたのか（承認後も保持されていたのか、決済処理中に傍受されたのか）を説明していない。

技術的な補足: CVVが流出する経路は大きく2つ考えられる。(1) サーバー側のログ・デバッグ出力・一時テーブル・メッセージキューなどに意図せず残っていた場合、(2) チェックアウトページのJavaScript改ざん（Webスキミング／Magecart型）やサーバー側決済処理への介入により入力中・処理中のデータが傍受された場合。どちらかは公表されていない。Cleverbridgeはマーチャント・オブ・レコードとして多数のソフトウェアベンダーの決済ページを代行しているため、利用者は「購入したソフトの販売元」ではなく決済代行事業者から通知を受け取る点に注意が必要で、これを装うフィッシングも想定される。自社で決済フォームを持つ事業者は、PCI DSS v4のRequirement 6.4.3／11.6.1（決済ページ上のスクリプトの承認・完全性確認・改ざん検知）の実装状況と、アプリケーションログにカードデータが出力されていないことを確認したい。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

- なし
