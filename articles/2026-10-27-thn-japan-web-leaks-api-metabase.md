# 日本でWeb経由の情報漏えいが急増、モバイルAPI悪用とMetabase攻撃（The Hacker News）

- **日付**: 2026-10-27
- **出典**: [The Hacker News](https://thehackernews.com/2026/10/japan-sees-sharp-rise-in-web-data-leaks.html)
- **トピック**: [国内Webサービス・アプリを狙う相次ぐ不正アクセスとJPCERT/CC・内閣サイバー注意喚起（2026年9〜10月）](../topics/jpcert-domestic-app-api-attacks-2026.md)
- **分類**: 続報

## 概要

The Hacker Newsが、JPCERT/CCの10月8日付注意喚起を引用し、日本でWebシステム経由の個人情報漏えいが急増していると報じた。公開スマホアプリの解析によるAPI悪用と既知脆弱性が主因とされる。

## 詳細

- **規模**: Macnicaの集計で10月6日までに119件の公表事案。
- **手口**: 公開アプリを逆コンパイルしてAPIエンドポイントとキーを抽出し、UIに出ない内部APIを直接呼び出す。
- **Metabase**: 二次情報ではCVE-2026-72898（認証不要のSQLi→管理者権限）の悪用が関連づけられ、JPCERT/CCは8月14日からMetabase関連の活動に言及。10月9日の更新でWARファイル経由のWebシェル設置も報じられたが、一次情報での確認が必要。
- **推奨対策**: APIの厳格な認可とレート制限、最小権限・短寿命トークンと失効、既知脆弱性の修正、不要サービスの非公開化。

---

## 関連記事

