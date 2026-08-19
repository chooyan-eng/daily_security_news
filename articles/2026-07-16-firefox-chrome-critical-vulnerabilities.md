# Firefox・Chrome等が複数の重大脆弱性を修正、Firefoxは2件でエクスプロイトコード公開済み

- **日付**: 2026-07-16
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/firefox-chrome-adobe-and-vmware-updates.html), [Mozilla Security Advisory](https://www.mozilla.org/en-US/security/advisories/mfsa2026-67/), [SecurityWeek](https://www.securityweek.com/critical-vulnerabilities-patched-with-fresh-chrome-150-firefox-152-updates/)
- **分類**: 新規

## 概要

Mozillaが2026年7月にリリースしたFirefox 152.0.6で、エクスプロイトコードが既に公開されている2件の脆弱性（CVE-2026-15718、CVE-2026-15719）を修正。同時期にChrome 150、Adobe、VMwareからも複数の重大な脆弱性修正がリリースされている。

## 詳細

CVE-2026-15718は、FirefoxのJavaScript: WebAssemblyコンポーネントに存在する無効なポインタの問題。CVE-2026-15719は、DOM: Navigationコンポーネントに存在するサイト分離（site isolation）の不備で、悪意あるサイトが本来分離されているはずの別オリジンの情報や動作に影響を及ぼす恐れがある。

Mozillaはセキュリティアドバイザリの中で「この脆弱性に対するエクスプロイトコードは公開されているが、この不具合を悪用する実際の攻撃は確認していない」と述べており、実環境での悪用は未確認としながらも、PoCが既に流通している状況を踏まえ速やかなアップデートを推奨している。両脆弱性はFirefox 152.0.6で修正済み。

同時期にGoogleもChrome 150で複数の重大脆弱性を修正しており、Adobe・VMwareも各製品で重大なセキュリティアップデートをリリースしている。ブラウザはWebアプリケーションの実行基盤そのものであり、エクスプロイトコードが公開された状態での未パッチ利用は、フィッシングサイトや侵害されたWebサイト経由での攻撃リスクを高める。組織・個人ともに速やかなアップデート適用が推奨される。
