# Discordボット「Double Counter」、廃止サーバー上の脆弱なMetabase経由で侵害、約12GBを窃取

- **日付**: 2026-10-07
- **出典**: [Dexerto](https://www.dexerto.com/gaming/discord-bot-built-to-stop-alt-accounts-leaks-millions-of-users-ip-addresses-3416371/)
- **トピック**: [Metabase SQLインジェクションゼロデイ（CVSS 10.0、2026年8月）](../topics/metabase-sqli-zeroday-2026.md)
- **分類**: 続報

## 概要

Discordのサードパーティボット「Double Counter」は、2026年10月4日に攻撃者が約6時間クラウド環境に侵入し約12GBを複製したと公表した。起点は廃止予定のOVHサーバー上の脆弱なMetabaseと報じられている。

## 詳細

- Discord本体の侵害ではない。
- 約2,800万Discordアカウント分のユーザー名・IPアドレス・市区町村レベルの位置情報・ISP情報に関わるが、この数値は推定で、レコードは「部分的に複製され、露出扱い」とされる。
- メールアドレスは、Have I Been Pwned登録が約27.5万件、同社の表では約100万件と報道間で差がある。
- 窃取したボットトークンで約50の大規模Discordサーバーに攻撃者サーバーへの招待が投稿され、別製品のStripeキーで約7,316ドルの不正課金も発生（顧客資金は無事とされる）。
- 同社は認証情報を失効、ボットをリセットし14のクラウドプロジェクトを監査。Discordは新規インストールを制限したとの報道もある。
- 教訓: 廃止予定の資産に残った未パッチのBIツールが侵入口となった。CVE-2026-72898はKEV掲載済みで、資産棚卸しとパッチ適用が重要。

---

## 関連記事

