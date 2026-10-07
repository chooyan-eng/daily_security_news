# 改ざんされた正規サイトが偽Cloudflare認証でLunex/Psychedelic Stealerを配布するClickFixキャンペーン

- **日付**: 2026-10-07
- **出典**: [The Hacker News ほか](https://thehackernews.com/2026/09/lunex-stealer-abuses-amd-driver-to.html)
- **トピック**: [Lunex Stealer／ClickFixキャンペーン（2026年9月〜10月）](../topics/lunex-stealer-clickfix-2026.md)
- **分類**: 新規

## 概要

侵害された中小企業サイト100件超に不正なiframeが埋め込まれ、偽のCloudflare認証画面からWindowsの実行ダイアログへコマンド貼り付けを促し、MSI経由でLunex MaaS系のPsychedelic Stealerに感染させる手口が報じられている。BYOVDで防御を無効化する。

## 詳細

報告（Ontinue、Arctic Wolf等）による感染チェーン: 改ざんサイトに隠しiframeを挿入→偽Cloudflare確認画面がクリップボードにmsiexecコマンドをコピー→被害者が[Win]+[R]に貼り付け実行→MSIをダウンロード→CMSTPLUA COMオブジェクトでUACバイパス→AMD Radeon関連の脆弱ドライバPDFWKRNL.sys（CVE-2023-20598）を悪用するBYOVDでセキュリティ監視を無効化→7種のChromium系ブラウザの認証情報、暗号資産ウォレットを窃取し、PowerShellベースのNative Messaging Host経由で永続的なファイルシステムアクセスを確立する。

侵害されたのは美容クリニック、模型メーカー、書店、工具販売店など小規模事業者のサイトで、Webサイト運営者にとってはCMS・プラグイン更新、管理者認証の保護、サイト改ざん監視が重要。利用者側には「Webページが貼り付けコマンド実行を求めたら中止する」教育が有効。別系統でGhost CMSの欠陥を悪用し700超のサイトを改ざんするClickFixキャンペーンも報告されている。

参考: [Security Affairs](https://securityaffairs.com/?p=199731)、[Malwarebytes](https://www.malwarebytes.com/blog/threat-intel/2026/07/fake-google-and-cloudflare-verification-pages-spread-multiple-malware-families)

---

## 関連記事


