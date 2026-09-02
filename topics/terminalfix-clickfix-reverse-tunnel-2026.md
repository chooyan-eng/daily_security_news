# TerminalFix ClickFix亜種によるリバーストンネル攻撃キャンペーン（2026年）

## 概要

Microsoftが報告した新種のClickFix亜種「TerminalFix」。侵害された正規Webサイト上に偽のCloudflare CAPTCHA画面を表示し、被害者にWindows Terminal／PowerShellで悪性コマンドを実行させる。DLLサイドローディング、ステガノグラフィによるペイロード隠蔽、Active Directory偵察、独自のリバーストンネル実装を組み合わせた多段階攻撃チェーンを特徴とする。

**同一性の判断に役立つ情報：**
- キャンペーン名: TerminalFix（ClickFix技術の亜種）
- 報告元: Microsoft Security Blog（2026年8月28日公開）
- 手口: 侵害Webサイト上の偽Cloudflare CAPTCHA → Windows Terminal／PowerShellでのコマンド実行誘導
- 攻撃チェーン: DLLサイドローディング、ステガノグラフィによるペイロード抽出、AD偵察、独自リバーストンネル実装による永続的プロキシアクセス
- 検知ポイント: 非標準パスからの`LockScreenContentServer.exe`実行、不審なPowerShellアクティビティ、隠しペイロードディレクトリ、異常な外向き通信

## タイムライン

- [2026-09-01 新種ClickFix亜種「TerminalFix」、偽Cloudflare CAPTCHAで侵害サイト経由のリバーストンネル攻撃を展開](../articles/2026-09-01-terminalfix-clickfix-reverse-tunnel.md)
