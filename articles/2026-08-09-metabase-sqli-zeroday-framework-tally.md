# Metabaseの未認証SQLインジェクション ゼロデイが実際に悪用、Framework・Tallyが顧客データ窃取を公表

- **日付**: 2026-08-08
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/metabase-zero-day-exploited-in-wild.html) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/framework-tally-disclose-metabase-data-theft-attacks/)
- **トピック**: [Metabase 未認証SQLインジェクション ゼロデイ（2026年8月）](../topics/metabase-sqli-zeroday-2026.md)
- **分類**: 新規

## 概要

BIツール「Metabase」に、外部公開されている `POST /api/session/reset_password` エンドポイントを経由した未認証SQLインジェクション脆弱性（CVSS 10.0、CVE番号は未割当）が発見され、実際の攻撃で悪用されていることが判明した。攻撃者はログイン不要でMetabaseアプリケーションデータベースに任意のSQL文を注入し、管理者権限を奪取できる。Metabase Cloud自体が2026年8月3日に侵害され、顧客企業のFrameworkとTallyが顧客データ窃取被害を公表した。

## 詳細

### 脆弱性の内容

本脆弱性は、パスワードリセット機能のエンドポイント `POST /api/session/reset_password` に存在する未認証SQLインジェクションで、バージョン58から63までの全リリース（Metabase CloudのSaaS版・セルフホスト版の両方）に影響する。攻撃者はログインすることなく、このエンドポイントを通じてMetabaseのアプリケーションデータベースに直接SQL文を注入できる。

侵入後、攻撃者はアプリケーション設定の変更、接続されている外部データベースの認証情報の窃取、それらのデータベース経由でアクセス可能なあらゆるデータの読み取り・エクスポートが可能になる。BIツールという性質上、Metabaseには通常、社内の複数の重要データベースへの接続情報が集約されているため、被害はMetabase自体にとどまらず接続先データベース全体に及ぶ可能性がある。

### 発覚の経緯

Metabaseは自社のMetabase Cloud SaaSプラットフォームが2026年8月3日に何者かによってこの未知の脆弱性を用いて侵害されたことを検知し、悪用されたエンドポイントを即座にブロックした上で、数時間以内に修正パッチを適用した。Metabase Cloudの全顧客は自動的にアップグレードされ保護された。

### 被害企業

この脆弱性を悪用したデータ窃取攻撃について、少なくとも2社が被害を公表している。FrameworkとTallyはいずれも、氏名・住所・電話番号・メールアドレスを含む顧客情報への不正アクセスを受けたと報告した。

### 教訓

パスワードリセットのような「未認証でも到達可能であることが前提の機能」に重大な入力検証の欠陥が存在した場合、被害範囲は単一アプリケーションを超え、BIツールが接続する下流のデータベース群にまで連鎖する典型例であり、SaaS型BIツールのセキュリティ境界設計の重要性を改めて示している。

---

## 関連記事

なし（新規トピック）
