# Google、Chrome 152で26件の脆弱性を修正 Shared Tab Groups・WebGLに致命的なUse-After-Free

- **日付**: 2026-09-01
- **出典**: [Malwarebytes](https://www.malwarebytes.com/blog/bugs/2026/09/two-critical-chrome-flaws-put-users-at-risk-on-malicious-websites), [gbhackers](https://gbhackers.com/google-patches-26-chrome-vulnerabilities/), [cybersecuritynews](https://cybersecuritynews.com/google-fixes-26-chrome-vulnerabilities/)
- **トピック**: [Chrome 152 セキュリティアップデート（2026年9月）](../topics/chrome-152-security-update-2026.md)
- **分類**: 新規

## 概要

Googleは2026年9月、Chrome 152（Windows/macOS版152.0.7977.75/.76、Linux版152.0.7977.75）を公開し、26件の脆弱性を修正した。うち2件はCritical（致命的）評価のUse-After-Free脆弱性で、Shared Tab Groups機能とWebGLに存在する。悪用された場合、サンドボックス外での任意コード実行につながる可能性がある。

## 詳細

今回の更新で修正されたCritical評価の脆弱性の1つ、CVE-2026-84353はShared Tab Groups機能に存在するUse-After-Free脆弱性である。ソーシャルエンジニアリングと組み合わせた細工済みHTMLページを介して、リモートの攻撃者がブラウザのサンドボックス外で任意コードを実行できる可能性があるとされる。もう1件のCritical脆弱性はWebGL関連のUse-After-Freeで、同様に細工されたWebコンテンツによりChromeのクラッシュやブラウザプロセス内での制御奪取につながる恐れがある。

これら2件を含め、合計26件の脆弱性が今回のアップデートで修正された。Googleは現時点で、修正された脆弱性のいずれかが実際に悪用されているかどうかを明らかにしていない。Stable channelへの更新は数日から数週間かけて段階的に展開される。

Chromeは全世界で最も利用者の多いブラウザであり、Use-After-Free系の脆弱性は攻撃者にとってリモートコード実行の足がかりとして高い価値を持つ。企業・個人ともに、自動更新の適用状況を確認し、可能な限り早期にバージョン152への更新を完了させることが推奨される。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
