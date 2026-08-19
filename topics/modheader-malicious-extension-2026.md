# ModHeader 悪性ブラウザ拡張機能（2026年）

## 概要

Chrome・Edge向けに合計約160万インストールを持つHTTPヘッダー編集拡張機能「ModHeader」の公式ストア版に、閲覧ドメインを収集し外部サーバー（api.stanfordstudies.com）へ送信する隠し機能が発見された事件。収集機能は空のアローリストにより実際には無効化された「休眠」状態だったが、リモートから有効化できる設計だった可能性が指摘されている。Microsoftが2026年7月3日にEdgeストアから、Googleが7月10日にChromeウェブストアから削除した。

**同一性の判断に役立つ情報：**
- 対象拡張機能: ModHeader（HTTPヘッダー編集ツール）
- インストール数: 約160万（Chrome+Edge合計）
- 発見: 英セキュリティ企業 Stripe OLT
- 隠し機能: 閲覧ドメイン収集 → AES-GCM暗号化 → api.stanfordstudies.com/app/log へ日次送信
- 偽装ファイル名: dayjs.min-*.js（dayjsライブラリを装う）
- Edge削除日: 2026年7月3日
- Chrome削除日: 2026年7月10日
- 特記事項: 収集機能はアローリストが空のため実際には未発火（休眠状態）

## タイムライン

- [2026-07-13 160万インストールのブラウザ拡張機能「ModHeader」に隠された閲覧履歴収集機能、Google/Microsoftが削除](../articles/2026-07-13-modheader-malicious-browser-extension.md)
