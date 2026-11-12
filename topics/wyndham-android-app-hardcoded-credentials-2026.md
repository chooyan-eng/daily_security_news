# Wyndham Android アプリ ハードコード認証情報による顧客データ露出（2026年11月）

## 概要

ホテル大手 Wyndham の Android アプリにデータベースのパスワードがハードコードされており、Salesforce 上の内部データベース（氏名・メールアドレス・会員番号・ログイントークン、数百万エントリ規模）にアクセス可能だった事案。研究者 Robert Wiggins 氏（What Security）が AI ツールを用いて発見、TechCrunch が2026年11月上旬に報道。Wyndham は認証情報を失効。同氏は10月末にも Applebee's アプリで同種の問題を公表している。

## タイムライン

- [2026-11-12 Wyndham の Android アプリにDBパスワードがハードコード、会員情報・トークンが露出](../articles/2026-11-12-wyndham-android-app-hardcoded-credentials.md)
