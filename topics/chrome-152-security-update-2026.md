# Chrome 152 セキュリティアップデート（2026年9月）

## 概要

Google Chrome 152（2026年9月公開）で修正された26件の脆弱性に関するトピック。うち2件はCritical評価のUse-After-Free（Shared Tab Groups: CVE-2026-84353、WebGL）で、細工されたWebコンテンツによりサンドボックス外での任意コード実行につながる可能性がある。

**同一性の判断に役立つ情報：**
- 対象製品: Google Chrome 152（Windows/macOS版152.0.7977.75/.76、Linux版152.0.7977.75）
- 修正件数: 26件（9月1日）＋緊急パッチ12件（9月3日）
- Critical脆弱性: CVE-2026-84353（Shared Tab GroupsのUse-After-Free）、WebGL関連のUse-After-Free
- 実悪用が確認された脆弱性: CVE-2026-85046（V8エンジンのタイプコンフュージョン、CISA KEV追加）
- 公開日: 2026年9月1日（定例更新）、2026年9月3日（ゼロデイ対応の緊急パッチ）

## タイムライン

- [2026-09-01 Google、Chrome 152で26件の脆弱性を修正 Shared Tab Groups・WebGLに致命的なUse-After-Free](../articles/2026-09-01-chrome-152-security-update.md)
- [2026-09-06 Chrome 152緊急アップデート、実悪用中のV8ゼロデイCVE-2026-85046を修正](../articles/2026-09-06-chrome-v8-zeroday-cve-2026-85046.md)
