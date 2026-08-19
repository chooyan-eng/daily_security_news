# Chrome 151、重大7件を含む370件のセキュリティ脆弱性を修正——週2回のセキュリティリリース体制を試験中

- **日付**: 2026-08-01
- **出典**: [SecurityWeek](https://www.securityweek.com/chrome-151-patches-370-vulnerabilities/) / [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/google-patches-370-vulnerabilities/) / [Cybersecurity News](https://cybersecuritynews.com/chrome-151-patches-370-security-flaws/amp/)
- **トピック**: [Chrome V8 ゼロデイ脆弱性シリーズ（2026年）](../topics/chrome-zero-day-2026.md)
- **分類**: 関連

## 概要

Googleは2026年7月29日、Chrome 151（Windows/Mac版151.0.7922.71/.72、Linux版151.0.7922.71）を公開し、重大7件を含む370件のセキュリティ脆弱性を修正した。同社は週2回のセキュリティリリース体制への移行を試験中で、組織のパッチ適用ポリシー見直しが求められている。

## 詳細

Chrome 151で修正された重大（Critical）severityの脆弱性は7件。内訳は、Compositing・Views・Skia・Ozoneの各コンポーネントにおけるUse-After-Free（解放後使用）が4件、DawnおよびANGLEにおける信頼できない入力の検証不備が2件、Updaterにおける重大な競合状態（レースコンディション）が1件となっている。

本アップデートに先立ち、Googleは7月30日にもChrome 149・150向けの累積パッチとして合計1,072件のセキュリティバグ修正を公表しており、短期間に大規模な脆弱性修正が連続している。Googleは現在、従来の隔週から週2回へとセキュリティリリースの頻度を引き上げる体制を試験導入中であり、これに伴い企業のパッチ管理・展開ポリシーも高頻度リリースを前提に見直すことが推奨されている。

アップデートは7月29日からWindows・macOS・Linux向けに順次ロールアウトが開始されており、完全な展開までには数日〜数週間を要する見込み。今回のリリースで積極的な悪用が確認されている脆弱性は報告されていないが、Chromeでは過去にV8エンジンのゼロデイ脆弱性が複数回実際に悪用された実績があるため（参照: Chrome V8 ゼロデイ脆弱性シリーズ）、ユーザー・組織は速やかなアップデート適用が推奨される。

---

## 関連記事

- [Chrome V8 ゼロデイ CVE-2026-11645 が野生で悪用確認・即時アップデートを推奨](../articles/2026-06-22-chrome-v8-zero-day-cve-2026-11645.md) - 同じChromeブラウザの脆弱性対応であり、過去に実際の悪用実績があるコンポーネント（V8エンジン）を含む定期パッチという文脈で関連
