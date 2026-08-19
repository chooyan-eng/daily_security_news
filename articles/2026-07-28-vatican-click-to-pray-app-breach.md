# バチカンの祈祷アプリ「Click To Pray」、未認証API脆弱性で70万人以上の個人情報が半年以上流出

- **日付**: 2026-07-28
- **出典**: [Malwarebytes](https://www.malwarebytes.com/blog/privacy/2026/07/vaticans-click-to-pray-app-exposed-personal-data-from-700000-users), [Cybernews](https://cybernews.com/news/vatican-prayer-app-exposes-data/), [Tom's Hardware](https://www.tomshardware.com/tech-industry/cyber-security/security-flaw-in-vaticans-click-to-pray-app-leaves-over-700-000-global-users-exposed-app-has-been-leaking-user-data-for-over-six-months-and-still-does)
- **トピック**: [バチカン公式祈祷アプリ「Click To Pray」個人情報流出（2026年）](../topics/vatican-click-to-pray-app-breach-2026.md)
- **分類**: 新規

## 概要

ローマ教皇庁が提供する祈祷アプリ「Click To Pray」で、認証不要のAPIエンドポイントから70万人以上のユーザーの氏名・メールアドレス・国籍・生年月日等が取得可能な状態が半年以上放置されていたことが判明。研究者BobDaHackerが2026年1月に報告したが対応がなく、メディアの取材を経てようやく修正された。

## 詳細

セキュリティ研究者BobDaHackerは2026年1月、バチカンの公式祈祷アプリ「Click To Pray」のAPIに認証機構が存在しないことを発見した。連番のユーザーIDをURLに指定するだけで、ログインなしに任意アカウントの氏名、メールアドレス、居住国、生年月日、アカウントの役割（一般ユーザー／管理者等）、アカウント削除ステータスなどの個人情報を取得できた。加えてレート制限も存在せず、自動化されたGETリクエストを連続送信することでデータベース全体を一括ダウンロードすることも技術的に可能だった。

同研究者は発見後すぐにバチカン側へ報告を行ったが、6か月間まったく応答がなかったという。事態が動いたのは、研究者がジャーナリストに連絡し、そのジャーナリストがバチカンに正式に問い合わせを行ったことがきっかけで、Dark Readingによる報道を経て2026年7月25日前後についに脆弱性が修正された。

流出した情報自体は氏名やメールアドレスなど機微性の高い情報ではないものの、対象ユーザーには高齢者や信仰心の篤い層が多く含まれるとみられ、氏名とメールアドレスの組み合わせはフィッシング詐欺の格好の材料になりうるとMalwarebytesは警告している。今回のケースは、公的機関・非営利団体が運営するアプリであっても基本的なAPI認証設計（オブジェクトレベル認可、レート制限）が欠如し得ることを示す事例として注目されている。
