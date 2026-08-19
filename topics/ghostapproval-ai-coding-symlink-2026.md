# GhostApproval：AIコーディングアシスタントのシンボリックリンク信頼境界欠陥（2026年7月）

## 概要

Wizが2026年7月8日に公表した、AIコーディングアシスタントに共通する信頼境界の欠陥「GhostApproval」。悪意あるリポジトリ内のシンボリックリンクを使い、ユーザーが承認したファイル書き込みの実体を偽装し、SSH認証鍵などの機密ファイルを上書きさせる。Amazon Q Developer・Anthropic Claude Code・Augment・Cursor・Google Antigravity・Windsurfの6製品が対象。Amazon Q（CVE-2026-12958）とCursor（CVE-2026-50549）は修正済み、Anthropicは脆弱性として認めていない。

**同一性の判断に役立つ情報：**
- 発見者/命名: Wiz（GhostApproval）
- 対象製品: Amazon Q Developer、Anthropic Claude Code、Augment、Cursor、Google Antigravity、Windsurf
- 攻撃手法: 悪意あるリポジトリ内のシンボリックリンクによるファイル書き込み先偽装（インフォームドコンセントの回避）
- CVE: CVE-2026-12958（Amazon Q Developer、修正済み）、CVE-2026-50549（Cursor v3.0で修正済み）
- Anthropicの立場: バグとして非認定（v2.1.32でシンボリックリンク警告を実装済みと主張）
- 公表日: 2026年7月8日

## タイムライン

- [2026-07-09 「GhostApproval」：AIコーディングアシスタント6製品に共通するシンボリックリンク信頼境界の欠陥](../articles/2026-07-09-ghostapproval-ai-coding-assistant-symlink.md)
