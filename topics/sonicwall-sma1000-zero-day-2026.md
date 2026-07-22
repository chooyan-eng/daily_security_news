# SonicWall SMA1000 ゼロデイ連鎖悪用（CVE-2026-15409 / CVE-2026-15410）

## 概要

脅威アクター「UTA0533」が、SonicWall SMA1000シリーズVPNアプライアンスのSSRF脆弱性（CVE-2026-15409）とパストラバーサル脆弱性（CVE-2026-15410）を連鎖させ、SonicWallが2026年7月14日に公表・修正するより数週間前（6月22日ごろ）から積極的に悪用していた事案。ルート権限で動作するカスタムマルウェア「ROOTRUN」「KNUCKLEBALL」を展開し、通信傍受や横展開を試みた。

**同一性の判断に役立つ情報：**
- 脅威アクター: UTA0533
- 対象製品: SonicWall SMA1000シリーズ（6210・7210・8200v）
- 関連CVE: CVE-2026-15409（SSRF、/wsproxyエンドポイント）、CVE-2026-15410（パストラバーサル、execRemoveHotfix）
- 展開マルウェア: xzfind（ROOTRUN、setuid root実行ツール）、KNUCKLEBALL（Pythonベースインプラント、deploy_new.py）
- 悪用開始（推定）: 2026年6月22日ごろ
- 公表・修正日: 2026年7月14日（ホットフィックス12.4.3-03453 / 12.5.0-02835）

## タイムライン

- [2026-07-22 SonicWall SMA1000シリーズ、脆弱性開示前から数週間ゼロデイ悪用されカスタムマルウェア展開](../articles/2026-07-22-sonicwall-sma1000-zero-day-exploited.md)
