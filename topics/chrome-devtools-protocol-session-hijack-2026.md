# Chrome DevTools Protocol悪用セッションハイジャック手法（2026年）

## 概要

セキュリティ企業SpecterOpsが公開した、Windows上で稼働中のChrome/Edgeプロセス内部からChrome DevTools Protocol（CDP）のデバッグサーバーを有効化し、Cookie・保存パスワード・認証済みセッションを窃取するポストエクスプロイト技術「CDP-Enable-BOF」。Chrome/Edge自体の脆弱性ではなく、既にホスト上でコード実行権限を得た攻撃者が使う侵害後の手法。

**同一性の判断に役立つ情報：**
- 手法名: CDP-Enable-BOF
- 公開元: SpecterOps
- 公開日: 2026年8月14日
- 対象: Windows上のChrome/Edgeプロセス（chrome.exe / msedge.exe）
- 前提条件: ホスト上での既存のコード実行権限（CVE不要）
- 主要API: Storage.getCookies（Cookie取得）、Chromiumオートフィル機構（保存パスワード復元）
- 検知手段: Sysmon イベントID 8・10（プロセスインジェクション監視）

## タイムライン

- [2026-08-15 Chrome DevTools Protocolを悪用した新たなセッションハイジャック手法「CDP-Enable-BOF」が公開](../articles/2026-08-15-chrome-devtools-protocol-session-hijack.md)
