# Telegram for Android ウィジェット経由RCEと保護回避（2026年11月）

## 概要

Telegram for Androidで、ボットが送るウィジェット（JavaScriptランタイム）経由のRCE問題。Telegramは2026年11月上旬にseccompフィルタによる保護を追加したが、NebuSecが11月14〜17日に回避エクスプロイト2件（フィルタ対象外のウィジェットバグ／ウィジェットバグ＋カーネルバグの連鎖）を主張。Android版13.2.2（7303）で実証、テストサーバー上。CVE・修正版は未確認、第三者検証なし。本番は承認済みボットのみウィジェット送信可。

## タイムライン

- [2026-11-22 NebuSec、Telegram Android版の新しいウィジェット保護（seccompフィルタ）を回避するRCEエクスプロイト2件を主張](../articles/2026-11-22-telegram-android-widget-rce-bypass.md)
