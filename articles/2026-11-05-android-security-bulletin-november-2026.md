# Android 2026年11月セキュリティ公報、216件の脆弱性を修正（Critical 23件、RCE CVE-2026-58868）

- **日付**: 2026-11-05
- **出典**: [SecurityWeek](https://www.securityweek.com/androids-november-2026-updates-patch-over-200-vulnerabilities/amp/)
- **トピック**: [Android 2026年10月セキュリティ公報](../topics/android-security-bulletin-october-2026.md)
- **分類**: 続報

## 概要

Googleは11月のAndroid公報で216件の脆弱性を修正した(Critical 23件)。最も深刻なのはFrameworkのRCEでユーザー操作不要。CVE-2026-58868(Android runtime, RCE, Critical)はAndroid 14〜17に影響する。

## 詳細

公報によるとパッチレベル2026-11-05以降で対処済み。最重要はFrameworkコンポーネントの権限追加不要・ユーザー操作不要のリモートコード実行。CVE-2026-58868はAndroid runtimeのRCE(Critical、A-486464711)で、Android 14, 15, 16, 16-qpr2, 17が対象。11月3日時点でCISA KEVに該当Criticalはなく、悪用報告は確認できていない(要出典確認)。Frameworkの該当CVE番号は検索要約では特定できなかった。アプリ開発者もテスト端末のパッチレベルを更新したい。

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

- [Android 2026年10月セキュリティ公報](../articles/2026-10-17-android-security-bulletin-october.md) - 月例公報の前月分
