# 中国系脅威クラスター「UNK_MassTraction」、Roundcubeの脆弱性で北米大学の研究者を標的に

- **日付**: 2026-07-13
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-exploit-roundcube-flaw-to-spy-on-academic-researchers/), [The Hacker News](https://thehackernews.com/2026/07/suspected-china-aligned-hackers-exploit.html), [Proofpoint](https://www.proofpoint.com/us/blog/threat-insight/one-email-closer-edge-unkmasstraction-physics-exploitation)
- **トピック**: [UNK_MassTraction Roundcube悪用キャンペーン（2026年）](../topics/roundcube-unk-masstraction-2026.md)
- **分類**: 新規

## 概要

Proofpointが「UNK_MassTraction」と名付けた中国系とみられる脅威クラスターが、オープンソースWebメールクライアント「Roundcube」の既知の脆弱性2件（CVE-2024-42009、CVE-2025-49113）を連鎖させ、米国・カナダの大学の物理学・工学系部門の教職員を標的とするスパイ活動を行っていたことが判明した。2026年5月から観測されており、天体物理学・素粒子物理学や安全保障関連の研究に携わる組織が主な標的となっている。Roundcubeの脆弱性が中国系グループによって悪用された初の事例とされる。

## 詳細

### 攻撃チェーン

攻撃はメール経由で開始される。被害者が脆弱なRoundcube Webメールクライアントでメールを開くと、まずCVE-2024-42009（クロスサイトスクリプティング、CVSS 9.3）が発火し、被害者のブラウザ内でJavaScriptペイロード「IceCube」が実行される。IceCubeはRoundcubeに特化した情報窃取ツールで、ユーザー名・パスワード・クッキー・二要素認証(2FA)データ・ブラウザ情報などを収集する。

続いて、IceCubeの「ヘルパー」機能がサーバー側のCVE-2025-49113（デシリアライゼーションの脆弱性）を悪用し、Roundcubeサーバー自体で任意のPHPコードを実行できる状態に持ち込む。最終的にPHP製Webシェル「SquareShell」の設置を試みる。SquareShellはリモートコード実行機能を備えており、侵害後の持続的なアクセス確保に使われる。

### 標的と目的

標的は米国・カナダの大学における物理学・工学系部門の管理者や教授、および天体物理学・素粒子物理学・安全保障関連の研究に従事する組織。研究データやメール内容そのものを狙ったスパイ活動とみられている。

### 攻撃の位置づけ

Roundcubeの脆弱性は従来、ロシア系の国家支援型脅威アクターによる悪用が多く報告されてきたが、本件は中国系とみられるグループがRoundcubeの脆弱性を悪用した初めての確認事例とされ、攻撃者エコシステムの広がりを示すものとして注目されている。

### 対策

- Roundcubeを最新版へアップデートし、CVE-2024-42009・CVE-2025-49113が修正されたバージョンを使用すること
- 大学・研究機関では、物理学・工学系や安全保障関連部門を含め、Webメールクライアントの脆弱性管理を優先的に行うこと
- メール経由のXSSを起点とする攻撃チェーンに備え、メールクライアントのCSPやサンドボックス設定を強化すること
