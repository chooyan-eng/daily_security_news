# 新型ファイルレスバックドア「Mistic」と ランサムウェア IAB「KongTuke」の連携が明らかに

- **日付**: 2026-06-25
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/new-mistic-backdoor-linked-to-kongtuke.html)
- **トピック**: [Mistic バックドア・KongTuke IAB（2026年）](../topics/mistic-backdoor-kongtuke-2026.md)
- **分類**: 新規

## 概要

2026年6月25日、Symantec および Zscaler ThreatLabz が、保険・教育・IT・専門サービス分野を標的とする金融動機型攻撃に新型ファイルレスバックドア「Mistic」が使用されていることを報告した。Mistic はランサムウェア初期アクセスブローカー（IAB）「KongTuke」と関連し、Qilin・Interlock・Rhysida・Akira・8Base・Black Basta といった主要ランサムウェアグループへのアクセスを販売している。

## 詳細

### Mistic バックドアの技術的特徴

**ファイルレス実行**  
Mistic はペイロードをすべてメモリ上で実行し、ディスクへのファイル書き込みを行わない。従来のファイルスキャン型エンドポイント保護では検出が困難であり、Symantec はファイルスキャンでの検出では「見逃す」と警告している。

**自己削除機能（キルスイッチ）**  
長期・低可視性アクセスを維持することを優先する攻撃者の意図に沿って、自己削除機能を持ち、発見された際に痕跡を消去できる設計となっている。

**難読化**  
Zscaler ThreatLabz の解析によると、バックドアコードの約95%は自動解析ツールを混乱させるためのジャンク数学演算で構成されており、リバースエンジニアリング抵抗性が高い。

**DLL サイドローディング**  
正規の Microsoft 実行ファイルを使用した DLL サイドローディングによりマルウェアを読み込む。攻撃では偽のログイン画面を表示して認証情報を窃取するコンポーネントも併用された。

### KongTuke（IAB）との関連

Mistic は「MLTBackdoor」とも追跡されており、初期アクセスブローカー KongTuke（別名：404 TDS、Chaya_002、LandUpdate808、TAG-124、Woodgnat）に帰属されている。KongTuke は **ModeloRAT**（Python製RAT）とともに Mistic を展開し、侵害した企業ネットワークへのアクセスを複数のランサムウェアグループに販売している。

**KongTuke が供給するランサムウェアグループ**：
- Qilin
- Interlock
- Rhysida
- Akira
- 8Base
- Black Basta

### 標的分野と攻撃期間

- **標的**: 保険・教育・IT・専門サービス業
- **活動開始**: 2026年4月頃〜
- **地域**: 複数国（UK SMB を含む）

### 検出・対策

- インメモリ実行型のため、従来のファイルベーススキャンは無効
- 振る舞い検知・EDR による異常な DLL ロード・PowerShell 実行の監視が有効
- 偽のログイン画面による認証情報窃取への注意（MFA 強制が有効な対策）

---

## 関連記事

なし（新規トピック）
