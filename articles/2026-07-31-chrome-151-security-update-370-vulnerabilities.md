# Google、Chrome 151 で370件の脆弱性を修正 — Critical 7件を含む大型セキュリティアップデート

- **日付**: 2026-07-29
- **出典**: [SecurityWeek](https://www.securityweek.com/chrome-151-patches-370-vulnerabilities/)
- **トピック**: [Chrome 151 セキュリティアップデート（2026年7月）](../topics/chrome-151-security-update-2026.md)
- **分類**: 新規

## 概要

Googleは2026年7月29日、Chrome を バージョン151.0.7922.71/.72（Windows/macOS）・151.0.7922.71（Linux）に更新し、Critical 7件を含む合計370件の脆弱性を修正した。研究者への報奨金は合計58,500ドルに上る。段階的に全ユーザーへ配信される。

## 詳細

### 修正内容の内訳

Critical（最重大）7件のうち4件は Compositing・Views・Skia・Ozone の各コンポーネントにおけるUse-After-Free（解放後使用）の脆弱性。さらにDawnおよびANGLEにおける「信頼できない入力の検証不足」に分類されるCritical脆弱性2件、Updaterにおけるレースコンディションの脆弱性1件が含まれる。このほか、High 71件、Medium 170件、Low 122件の脆弱性が修正された。WebAudioにおけるType Confusionバグも報告されている。

### 位置づけ

本アップデートはChromeの定例セキュリティ更新であり、現時点で野生（in the wild）での悪用は報告されていない。2026年にはこれまでにも複数のChrome V8エンジンのゼロデイ脆弱性が実際に悪用される事例が続いていたが、今回のChrome 151アップデートはそれらとは別に、広範なコンポーネントを対象とした通常のセキュリティメンテナンスとして実施されたものである。

### 対応

Chromeユーザーは設定メニューから手動でアップデートを確認・適用することを推奨する。Chromiumベースの各種ブラウザ（Edge、Brave等）についても同様の修正が順次反映される見込み。

---

## 関連記事

なし（新規トピック）
