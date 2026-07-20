# SonicWall SMA 1000 VPNゼロデイチェーン・UTA0533（2026年）

## 概要

SonicWall Secure Mobile Access（SMA）1000シリーズVPNアプライアンスの脆弱性CVE-2026-15409（CVSS 10.0）とCVE-2026-15410（CVSS 7.2）を連鎖させ、root権限を奪取する攻撃キャンペーン。Volexityが「UTA0533」と追跡する脅威アクターにより、正式パッチ提供（2026年7月14日）の約3週間前、6月22日頃からゼロデイとして悪用されていた。KNUCKLEBALL・Sou5・ORANGETAILといったSMA固有のメモリ内インプラントを使用。

**同一性の判断に役立つ情報：**
- 脅威アクター: UTA0533（Volexityによる命名、未文書化のグループ）
- CVE: CVE-2026-15409（CVSS 10.0）、CVE-2026-15410（CVSS 7.2）
- 対象製品: SonicWall SMA 1000シリーズ VPNアプライアンス
- ゼロデイ悪用開始推定: 2026-06-22頃
- パッチ公開日: 2026-07-14（ホットフィックス 12.4.3-03453 / 12.5.0-02835）
- マルウェア: KNUCKLEBALL、Sou5、ORANGETAIL（いずれもメモリ内注入型）

## タイムライン

- [2026-07-20 SonicWall SMA 1000 VPNアプライアンス、公開前からゼロデイ悪用でroot権限奪取 – 脅威アクターUTA0533](../articles/2026-07-20-sonicwall-sma-zero-day-uta0533.md)
