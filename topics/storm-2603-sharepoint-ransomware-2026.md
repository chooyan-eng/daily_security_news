# Storm-2603 SharePoint 脆弱性悪用・ランサムウェアキャンペーン（2026年）

## 概要

脅威アクター Storm-2603 が、未修正のオンプレミス Microsoft SharePoint サーバーを少なくとも2025年半ばから標的にしているキャンペーン。CVE-2025-49706・CVE-2025-49704（SharePoint Server RCE）等の公開済み脆弱性を悪用し、正規フォレンジックツール（Velociraptor）・Cloudflare トンネル・BYOVD 手法を組み合わせて侵入を深め、独自ツールセット「Project AK47」（バックドア・ランサムウェア・ローダー）を展開する。ランサムウェアは `.x2anylock` 拡張子を使用し、タイムスタンプ型キルスイッチを持つ。中国系APTとの関連が暫定的に指摘されている。

**同一性の判断に役立つ情報：**
- 脅威アクター: Storm-2603（別名：CL-CRI-1040）
- 標的: 未修正オンプレミス SharePoint サーバー
- 主要悪用 CVE: CVE-2025-49706・CVE-2025-49704・CVE-2025-11371
- ツールセット名: Project AK47（バックドア + ランサムウェア + ローダー）
- ランサムウェア拡張子: `.x2anylock`
- BYOVD ドライバー: NSecKrnl.sys
- C2 手法: Cloudflare トンネル・Zoho Assist・Visual Studio Code SSH
- 中国系APT 関連: Palo Alto Unit 42 が暫定的に指摘
- 帰属研究: Unit 42（Project AK47）・Microsoft（Storm-2603）

## タイムライン

- [2026-06-25 Storm-2603 が未修正 SharePoint サーバーを悪用：ランサムウェアとカスタムバックドア「Project AK47」を展開](../articles/2026-06-25-storm-2603-sharepoint-backdoor-ransomware.md)
