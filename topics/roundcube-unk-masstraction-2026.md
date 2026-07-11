# UNK_MassTraction Roundcube悪用キャンペーン（2026年）

## 概要

Proofpointが追跡する中国系とみられる脅威クラスター「UNK_MassTraction」が、Roundcube Webmailの既知脆弱性チェーン（CVE-2024-42009・CVE-2025-49113）を悪用し、米国・カナダの大学（国家安全保障関連部門、天体物理学・素粒子物理学研究者）を標的にスパイ活動を行っているキャンペーン。2026年5月頃から活動が観測されている。

**同一性の判断に役立つ情報：**
- 脅威アクター: UNK_MassTraction（Proofpointによる命名）
- 帰属: 中国系の可能性（中国語アーティファクトを一部フィッシングメールで確認）
- 標的: 米国・カナダの大学（国家安全保障関連部門、天体物理学・素粒子物理学研究者）
- 悪用CVE: CVE-2024-42009（CVSS 9.3）、CVE-2025-49113
- 対象ソフトウェア: Roundcube Webmail
- 手口: ブラウザ内JavaScript実行 → 認証情報窃取 → Webシェル設置 or VShell展開
- 活動観測開始: 2026年5月頃

## タイムライン

- [2026-07-11 中国系ハッカークラスター「UNK_MassTraction」、Roundcube Webmailの脆弱性を悪用し北米大学の研究者を標的に](../articles/2026-07-11-roundcube-webmail-china-unk-masstraction-universities.md)
