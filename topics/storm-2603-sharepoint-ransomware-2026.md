# Storm-2603 SharePoint 脆弱性悪用・ランサムウェアキャンペーン（2026年）

## 概要

脅威アクター Storm-2603 が、未修正のオンプレミス Microsoft SharePoint サーバーを少なくとも2025年半ばから標的にしているキャンペーン。CVE-2025-49706・CVE-2025-49704（SharePoint Server RCE）等の公開済み脆弱性を悪用し、正規フォレンジックツール（Velociraptor）・Cloudflare トンネル・BYOVD 手法を組み合わせて侵入を深め、独自ツールセット「Project AK47」（バックドア・ランサムウェア・ローダー）を展開する。ランサムウェアは `.x2anylock` 拡張子を使用し、タイムスタンプ型キルスイッチを持つ。中国系APTとの関連が暫定的に指摘されている。2026年7月には、新たに公開されたSharePointの逆シリアル化型RCE脆弱性CVE-2026-45659の悪用にも同グループの関与が確認され、継続的に新しい脆弱性を攻撃チェーンに組み込んでいることが判明した。

**同一性の判断に役立つ情報：**
- 脅威アクター: Storm-2603（別名：CL-CRI-1040）
- 標的: 未修正オンプレミス SharePoint サーバー
- 主要悪用 CVE: CVE-2025-49706・CVE-2025-49704・CVE-2025-11371・CVE-2026-45659
- ツールセット名: Project AK47（バックドア + ランサムウェア + ローダー）
- ランサムウェア拡張子: `.x2anylock`
- BYOVD ドライバー: NSecKrnl.sys
- C2 手法: Cloudflare トンネル・Zoho Assist・Visual Studio Code SSH
- 中国系APT 関連: Palo Alto Unit 42 が暫定的に指摘
- 帰属研究: Unit 42（Project AK47）・Microsoft（Storm-2603）
- 主要悪用 CVE: CVE-2025-49706・CVE-2025-49704・CVE-2025-11371・CVE-2026-23760・CVE-2026-45659
- ランサムウェア名/拡張子: Warlock ランサムウェア（`.x2anylock` 拡張子）
- CVE-2026-45659 KEV追加・連邦機関修正期限: 2026年7月4日
- ランサムウェア: `.x2anylock` 拡張子（Project AK47）／ Warlockランサムウェア（CVE-2026-45659経由）
- CVE-2026-45659 CISA KEV追加日: 2026-07-01（FCEB向けパッチ期限: 2026-07-04）

## タイムライン

- [2026-07-16 SharePoint RCE脆弱性CVE-2026-45659がCISA KEVに追加、Storm-2603による悪用が確認](../articles/2026-07-16-sharepoint-cve-2026-45659-storm2603.md)
- [2026-07-11 SharePoint RCE脆弱性CVE-2026-45659がCISA KEVに追加、Storm-2603によるWarlockランサムウェア展開に悪用](../articles/2026-07-11-sharepoint-cve-2026-45659-storm-2603-warlock-kev.md)
- [2026-07-05 SharePoint新CVE-2026-45659、Storm-2603がWarlockランサムウェア展開に悪用しCISA KEV追加](../articles/2026-07-05-sharepoint-cve-2026-45659-storm-2603-warlock.md)
- [2026-07-01 Microsoft SharePoint RCE（CVE-2026-45659）がCISA KEVに追加、実悪用を確認](../articles/2026-07-02-sharepoint-cve-2026-45659-kev.md)
- [2026-06-25 Storm-2603 が未修正 SharePoint サーバーを悪用：ランサムウェアとカスタムバックドア「Project AK47」を展開](../articles/2026-06-25-storm-2603-sharepoint-backdoor-ransomware.md)
