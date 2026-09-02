# 新種ClickFix亜種「TerminalFix」、偽Cloudflare CAPTCHAで侵害サイト経由のリバーストンネル攻撃を展開

- **日付**: 2026-09-01
- **出典**: [Microsoft Security Blog](https://www.microsoft.com/en-us/security/blog/2026/08/28/terminalfix-campaign-deploys-reverse-tunnel-through-multistage-intrusion/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/microsoft-warns-of-terminalfix-attacks-deploying-reverse-tunnels/), [The Hacker News](https://thehackernews.com/2026/08/terminalfix-uses-fake-cloudflare.html)
- **トピック**: [TerminalFix ClickFix亜種によるリバーストンネル攻撃キャンペーン（2026年）](../topics/terminalfix-clickfix-reverse-tunnel-2026.md)
- **分類**: 新規

## 概要

Microsoftは、正規のWebサイトが侵害されて表示される偽のCloudflare CAPTCHA画面を悪用し、被害者にWindows Terminal／PowerShellで悪性コマンドを実行させる新たなClickFix亜種「TerminalFix」を報告した。DLLサイドローディングやステガノグラフィによるペイロード隠蔽、Active Directory偵察、独自のリバーストンネル実装を組み合わせた多段階の侵入チェーンを特徴とする。

## 詳細

TerminalFixは、従来型のClickFix攻撃がWindowsの「ファイル名を指定して実行」ダイアログへ誘導するのに対し、同じ社会工学的手口をWindows TerminalやPowerShellへの誘導に応用した亜種である。攻撃者はあらかじめ侵害した正規Webサイト上に偽のCloudflare検証（CAPTCHA）オーバーレイを表示させ、訪問者に「人間であることの確認」と称してクリップボードにコピーしたコマンドをターミナルへ貼り付けて実行するよう誘導する。ターミナル経由の実行は、Runダイアログよりも複雑な複数行スクリプトを確実に実行させやすいという利点があるとされる。

実行されたコマンドを起点とする攻撃チェーンは多段階に及び、正規実行ファイルを悪用したDLLサイドローディング、画像データ内にペイロードを隠すステガノグラフィによる抽出、侵害端末が属するActive Directory環境の広範な偵察、そして攻撃者にネットワークレベルの持続的なプロキシアクセスを与える独自のリバーストンネル実装の展開までを含む。得られたアクセスは、水平展開・権限昇格・データ窃取など後続の攻撃活動の足がかりとなり得る。

Microsoftは防御側に対し、非標準パスからの`LockScreenContentServer.exe`の異常な実行、不審なPowerShellアクティビティ、隠しペイロードディレクトリ、および本キャンペーンに関連する異常な外向き通信の有無を調査するよう推奨している。正規サイトの改ざんを起点とする点で、Webアプリケーション運営者にとってもサイト改ざん対策・CSP等の重要性を再認識させる事例である。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
