# 中国系ハッカークラスター「UNK_MassTraction」、Roundcube Webmailの脆弱性を悪用し北米大学の研究者を標的に

- **日付**: 2026-07-11
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/suspected-china-aligned-hackers-exploit.html), [The Register](https://www.theregister.com/security/2026/07/08/suspected-chinese-snoops-caught-breaking-into-universities-roundcube-mailservers/), [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-exploit-roundcube-flaw-to-spy-on-academic-researchers/)
- **トピック**: [UNK_MassTraction Roundcube悪用キャンペーン（2026年）](../topics/roundcube-unk-masstraction-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業Proofpointは、中国系とみられる脅威クラスター「UNK_MassTraction」が、オープンソースWebメールソフトウェア「Roundcube」の既知の脆弱性を悪用し、米国およびカナダの大学（特に物理学・工学分野で国家安全保障に関連する部門や天体物理学・素粒子物理学の研究者）を標的にスパイ活動を行っていたと報告した。2026年5月頃から活動が観測されている。

## 詳細

### 攻撃の手口

UNK_MassTractionは、Roundcube Webmailに存在する既知の脆弱性チェーンを悪用する。まずCVE-2024-42009（CVSS 9.3）を用いて被害者のブラウザ内でJavaScriptを実行させ、次にCVE-2025-49113を悪用してメールサーバーへの足がかりを確立する。この2段階のエクスプロイトチェーンにより、認証情報を窃取した上で、持続的アクセスのためのWebシェルを設置するか、既知のポスト・エクスプロイトツール「VShell」を展開する。

標的となったのは主に、国家安全保障に関連する研究や天体物理学・素粒子物理学を専門とする学部の管理者・教授であり、研究成果や機密性の高い学術情報の窃取を狙ったスパイ活動と分析されている。

### 攻撃者の帰属

Proofpointは本クラスターを「UNK_MassTraction」として追跡しており、標的の選定パターン、インフラの関連性、一部フィッシングメールに含まれる中国語のアーティファクトから、中国と関連するスパイ活動を目的とした活動である可能性が高いと評価している。活動は少なくとも2026年5月から検知されている。

### Roundcubeの脆弱性が繰り返し狙われる背景

Roundcubeは多くの大学・研究機関・中小組織がセルフホストするWebメールクライアントとして広く利用されているが、パッチ未適用のインスタンスが多く残存しており、国家支援型攻撃者にとって継続的に有効な侵入経路となっている。CVE-2024-42009やCVE-2025-49113はいずれも既に修正パッチが提供されている既知の脆弱性であり、本事案はパッチ管理の遅れが標的組織の防御において依然として大きな課題であることを改めて示している。

## 対策・推奨事項

- Roundcubeを最新版に速やかにアップデートし、CVE-2024-42009・CVE-2025-49113を含む既知の脆弱性を解消する
- メールサーバーへの不審なログインおよびWebシェルの設置有無を監査する
- 高等教育機関・研究機関はセルフホスト型Webメールの露出を最小化し、多要素認証を導入する

---

## 関連記事

なし
