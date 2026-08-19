# 「GhostApproval」— シンボリックリンク悪用でClaude Code等6大AIコーディングアシスタントがワークスペース外へ書き込み可能に

- **日付**: 2026-07-08
- **出典**: [The Register](https://www.theregister.com/security/2026/07/08/bug-in-top-ai-coding-agents-shows-that-unix-era-security-headaches-never-really-die/5268025)
- **トピック**: [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md)
- **分類**: 関連

## 概要

Wiz Researchは、Amazon Q Developer・Anthropic Claude Code・Augment・Cursor・Google Antigravity・Windsurfの主要AIコーディングアシスタント6種に共通する脆弱性パターン「GhostApproval」を公開した。悪意あるリポジトリ内のシンボリックリンクを悪用し、AIエージェントにワークスペース外の機微なファイル（例：SSH認証鍵）への書き込みをさせることが可能。承認ダイアログには無害なファイル名しか表示されず、開発者は実際には何を承認しているか把握できない。

## 詳細

### 攻撃手法（シンボリックリンク悪用）

GhostApprovalは、古典的なUNIXのシンボリックリンク追従挙動を悪用する。攻撃者は `project_settings.json` という名前のファイルを、被害者の `~/.ssh/authorized_keys` を指すシンボリックリンクとして仕込んだ悪意あるリポジトリを用意する。README には「project_settings.json に1行追加してほしい」という指示が書かれており、その1行は無害な設定に見せかけた攻撃者自身のSSH公開鍵である。

開発者がAIエージェントに「ワークスペースをセットアップして」「READMEの指示に従って」と依頼すると、エージェントはシンボリックリンクをたどってそのSSH鍵を `authorized_keys` へ直接書き込んでしまう。

### 信頼境界の問題（UI偽装）

本脆弱性の核心は、承認ダイアログの誤表示にある。複数のツールにおいて、エージェントは実際には機微な場所（シンボリックリンクの参照先）へのファイル解決を行っているにもかかわらず、承認ダイアログには無害なファイル名のみが表示される。これはCWE-451（重要情報のUI偽装）がシンボリックリンク脆弱性の上に積み重なった構造であり、開発者は実際に何を承認しているか確認できないまま操作を承認してしまう。

### 影響を受けるツールとベンダー対応

対象6ツール：Amazon Q Developer、Anthropic Claude Code、Augment、Cursor、Google Antigravity、Windsurf

- **迅速に修正**: AWS、Cursor、Google の3社
- **受領を認めたが以降応答なし**: 2社
- **リスク受容として却下**: 1社（Anthropic）

Anthropicは、開発者がセッション開始時にフォルダを信頼し、その後編集を承認した以上、判断は開発者自身の責任であるとして「脅威モデルの範囲外」と回答している。

### 既存トピックとの関連

本脆弱性は、Check Point Researchが発見したClaude CodeのRCE脆弱性（CVE-2025-59536、`.claude/settings.json` のフック実行に起因）とは異なる攻撃経路（シンボリックリンク経由のファイル書き込み）だが、いずれも「悪意あるリポジトリを開く・READMEの指示に従う」という共通の攻撃導線を持ち、AIコーディングアシスタントにおけるサンドボックス境界・信頼境界の脆弱性という同じ系統の問題を示している。

---

## 関連記事

- [Claude Code RCE・APIキー窃取脆弱性（CVE-2025-59536/CVE-2026-21852）](../topics/claude-code-rce-cve-2025-59536.md) - 同じくAIコーディングアシスタントのサンドボックス・信頼境界に関する脆弱性
