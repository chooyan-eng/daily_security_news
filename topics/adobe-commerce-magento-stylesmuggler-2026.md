# Magento/Adobe Commerce ゼロデイ「StyleSmuggler」未認証RCE（2026年9月）

## 概要

ECプラットフォームMagento（Adobe Commerce含む）の全バージョンに影響する未認証リモートコード実行ゼロデイ「StyleSmuggler」。決済失敗レポート生成機能を悪用してテンプレートシステムの「styles」プロパティにPHPコードを注入し、決済失敗通知メール処理時にコードを実行させる2段階攻撃。セキュリティ企業Sansecが発見・命名。2026年9月7日時点でAdobeからCVE番号・パッチ・回避策は未提供。

**同一性の判断に役立つ情報：**
- 攻撃名: StyleSmuggler（Sansec命名）
- 対象製品: Magento Open Source / Adobe Commerce 全バージョン（2.4.9含む最新版も影響）
- 脆弱性種別: 未認証RCE、決済失敗レポート機能を悪用したPHPコード注入（stylesプロパティ経由）→決済失敗通知メール処理時に実行
- 発見・開示: Sansec（2026年9月5日開示）
- 実悪用開始: 開示前日の2026年9月4日から確認
- 攻撃後の挙動: Rust製の永続的バックドアバイナリを設置、外部C2サーバーと通信
- CVE番号: 2026年9月7日時点で未割当、Adobeからの公式パッチ・回避策も未提供

## タイムライン

- [2026-09-07 Magento/Adobe Commerceに未認証RCEゼロデイ「StyleSmuggler」、パッチ未提供のまま実悪用が拡大](../articles/2026-09-07-magento-adobe-commerce-stylesmuggler-zeroday.md)
