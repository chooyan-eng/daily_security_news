# Novo Nordisk、FulcrumSecの$25Mランサム拒否後に1.3TBデータ漏洩開始：Azure/GitHub認証情報が初期侵入経路

- **日付**: 2026-06-17
- **出典**: [SecurityWeek](https://www.securityweek.com/cybercrime-group-claims-novo-nordisk-hack/) / [Cybernews](https://cybernews.com/news/novo-nordisk-hackers-ozempic-data-sale/) / [BankInfoSecurity](https://www.bankinfosecurity.com/hackers-begin-to-leak-novo-nordisks-stolen-data-a-31989)
- **トピック**: [Novo Nordisk FulcrumSec データ窃取・恐喝事件（2026年6月）](../topics/novo-nordisk-fulcrumsec-2026.md)
- **分類**: 新規

## 概要

サイバー犯罪グループ FulcrumSec が、デンマークの製薬大手 Novo Nordisk（オゼンピック・ウゴービの製造元）から窃取した 1.3TB のデータの漏洩を 2026年6月15日に開始した。$25M のランサム要求を拒否された FulcrumSec は、臨床試験データ・AIモデル・患者データを含む盗難情報の「プライベート販売」を模索している。初期侵入にはクライアントサイドの JavaScript バンドルに埋め込まれた Azure コンテナレジストリ認証情報と GitHub PAT が使用された。

## 詳細

### FulcrumSec とは

FulcrumSec は 2025年10月に出現した比較的新しいサイバー恐喝グループ。ランサムウェアの展開ではなくデータ窃取と恐喝を主戦術とする（データ窃取型恐喝）。

### 攻撃のタイムライン

| 時期 | イベント |
|------|---------|
| 2026年3月 | Novo Nordisk の IT 環境への初期侵入 |
| 2026年3月〜5月 | 2ヶ月以上かけて内部を偵察・データ窃取 |
| 2026年5月 | $25M のランサム要求（拒否される） |
| 2026年6月15日 | データ漏洩を開始（サンプル公開） |
| 2026年6月17日現在 | 盗難データの「プライベート販売」を模索中 |

### 初期侵入手法

FulcrumSec が主張する初期侵入経路は2つ：

1. **Azure コンテナレジストリ認証情報の露出**
   - クライアントサイドの JavaScript バンドルに Azure コンテナレジストリの認証情報が含まれていた
   - 公開されたウェブアプリのフロントエンドコードから抽出

2. **GitHub Personal Access Token（PAT）の露出**
   - 数百のプライベートリポジトリへのアクセス権を持つ GitHub PAT が公開状態
   - 詳細な侵入経路は不明だが、ソースコードリポジトリへの広範なアクセスを可能にした

**教訓**: クライアントサイドコードや公開リポジトリへのシークレット埋め込みは、製薬企業のような高価値ターゲットでも深刻な初期侵入経路となる。

### 窃取されたデータの内容

FulcrumSec が主張する盗難データ（計 1.3TB）：

- **創薬データベース**: 創薬コラボレーションデータベース全体
- **臨床試験データ**: 約11,500名の仮名化患者データ
- **独自 AI モデル**: 創薬に使用するプロプライエタリ AI モデル
- **従業員情報**: 人事・従業員関連データ
- **その他 IP**: 知的財産、研究データ

### Novo Nordisk の対応

同社は TechRepublic の取材に対しセキュリティインシデントの発生を認め調査中と回答。ただし具体的なデータの範囲については確認していない。

### 推奨対応（業界全般）

- クライアントサイド JavaScript バンドルにシークレットが含まれていないかスキャン（例: `truffleHog`、`git-secrets`）
- GitHub リポジトリのシークレットスキャン機能を有効化
- Azure コンテナレジストリへのアクセス制御を最小権限原則で設計
- GitHub PAT の有効期限設定と定期的なローテーション
- 製薬・ライフサイエンス業界向けの脅威インテリジェンス強化（FulcrumSec の動向監視）
