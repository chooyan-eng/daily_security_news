# Chrome 152 セキュリティアップデート（2026年9月）

## 概要

Google Chrome 152（2026年9月公開）に関する一連のセキュリティアップデートのトピック。初回リリース（152.0.7977.75/.76）では26件の脆弱性を修正し、うち2件はCritical評価のUse-After-Free（Shared Tab Groups: CVE-2026-84353、WebGL）だった。9月3〜4日には追加の緊急アップデート（152.0.7977.82/.83）が公開され、実際に悪用が確認されたV8エンジンのゼロデイ脆弱性CVE-2026-85046を含む12件が修正された。

**同一性の判断に役立つ情報：**
- 対象製品: Google Chrome 152系列（Windows/macOS/Linux）
- 初回リリース: 152.0.7977.75/.76（2026年9月1日頃、26件修正、Critical: CVE-2026-84353ほか）
- 追加リリース: 152.0.7977.82/.83（2026年9月3〜4日、12件修正）
- ゼロデイ脆弱性: CVE-2026-85046（V8のType Confusion、CVSS8.8、実悪用確認済み、2026年の6件目のChromeゼロデイ）。ほかCVE-2026-85045（V8競合状態）、CVE-2026-85048（CompositingのUse-After-Free）も修正
- 悪用状況: CVE-2026-85046はGoogleが実悪用の存在を確認

## タイムライン

- [2026-09-04 Chrome、実悪用中のV8ゼロデイCVE-2026-85046を修正 2026年6件目のゼロデイ対応](../articles/2026-09-04-chrome-cve-2026-85046-zeroday.md)
- [2026-09-01 Google、Chrome 152で26件の脆弱性を修正 Shared Tab Groups・WebGLに致命的なUse-After-Free](../articles/2026-09-01-chrome-152-security-update.md)
