# Wyndham、Androidアプリ内にハードコードされたパスワードから顧客データベースが露出

- **日付**: 2026-11-09
- **出典**: [TechCrunch](https://techcrunch.com/2026/11/09/hotel-giant-wyndham-exposed-customer-data-after-app-security-lapse/)
- **トピック**: [Wyndham Androidアプリ ハードコード認証情報による顧客データ露出（2026年11月）](../topics/wyndham-android-app-exposure-2026.md)
- **分類**: 新規

## 概要

ホテル大手WyndhamのAndroidアプリのコード内にパスワードがハードコードされており、Salesforce上の社内データベースにアクセス可能だったことが判明した。顧客の氏名、メールアドレス、会員番号、ログイントークンが露出していた。同社は認証情報を失効させ、悪用の証拠はないとしている。

## 詳細

- **発見者**: What Security の Robert Wiggins 氏。AIツールを用いてアプリを解析し発見した。約2週間前のApplebee'sアプリでの同種の発見に続く2例目。
- **内容**: アプリのコードに埋め込まれたパスワードで、Salesforceでホストされた社内データベースにアクセスできた。顧客の氏名、メールアドレス、会員番号、ログイントークンが含まれていた。
- **規模**: 同氏によればデータベースには数百万件のエントリがあったが、正確な顧客件数は特定できていない。
- **対応**: Wyndhamには脆弱性の報告窓口がなく、同氏はTechCrunch経由で通知。同社は当該認証情報を失効させ、不正アクセスの証拠はないと説明。ただし、発見以前のアクセスを検証できるサーバーログを保有しているかについては回答していない。

技術的な補足: モバイルアプリのバイナリは配布された時点で攻撃者の手元にあり、難読化しても埋め込まれた秘密情報は抽出できる。アプリに入れてよいのは公開前提の識別子のみで、バックエンド（特にSalesforce等のSaaS）への特権的な認証情報は必ずサーバー側に置き、アプリはユーザー単位の短寿命トークンで自社APIを経由させるべきである。ログイントークンが保存データに含まれていた点は、アカウント乗っ取りに直結し得るため、失効とあわせてトークンの無効化が必要となる。LLMを使ったデコンパイル結果の解析により、この種の欠陥の発見コストが下がっている点も留意すべきで、報告窓口（security.txt等）の整備が望ましい。

出典: [TechCrunch](https://techcrunch.com/2026/11/09/hotel-giant-wyndham-exposed-customer-data-after-app-security-lapse/) / [TechRadar](https://www.techradar.com/pro/security/wyndham-confirms-it-exposed-hotel-customer-data-after-expert-finds-flaw-in-app-security) / [SC Media](https://www.scworld.com/brief/wyndham-addresses-security-flaw-in-android-app)

> 注: 本セッションでは外部サイトの本文を直接取得できず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

