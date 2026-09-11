# Novo Nordisk FulcrumSec データ窃取・恐喝事件（2026年6月）

## 概要

サイバー犯罪グループ FulcrumSec が Novo Nordisk（オゼンピック・ウゴービ製造元）から窃取した 1.3TB のデータを 2026年6月15日から公開し始めたキャンペーン。初期侵入にはクライアントサイド JavaScript バンドルに埋め込まれた Azure コンテナレジストリ認証情報と GitHub PAT が使用された。臨床試験データ（約11,500名分）、AIモデル、創薬データが含まれる。$25M のランサム要求は拒否されており、プライベート販売に移行。同グループはクライアント側JS・モバイルアプリ・公開リポジトリ等にハードコードされた認証情報を悪用する手口を「Hardcoded Horrorshow」と称し、マンチェスター空港グループ、Arup Group、Global Schools Groupなど他組織にも同様の手口で被害を拡大させている。

**同一性の判断に役立つ情報：**
- 脅威アクター: FulcrumSec（2025年10月出現）
- 被害組織: Novo Nordisk（デンマーク製薬大手）
- 盗難データ量: 1.3TB
- 初期侵入: 2026年3月
- 初期侵入手法: クライアントサイド JS バンドル内の Azure コンテナレジストリ認証情報、GitHub PAT
- ランサム要求: $25M（拒否）
- データ漏洩開始: 2026年6月15日
- 手口の呼称: 「Hardcoded Horrorshow」（クライアント側JS・モバイルアプリ・公開リポジトリのハードコード認証情報悪用）
- 他の被害組織: Manchester Airports Group、Arup Group、Global Schools Group 等

## タイムライン

- [2026-09-11 FulcrumSec、「Hardcoded Horrorshow」と称しクライアント側JS・モバイルアプリのハードコード認証情報を悪用する手口を継続](../articles/2026-09-11-fulcrumsec-hardcoded-horrorshow.md)
- [2026-06-17 Novo Nordisk、FulcrumSecの$25Mランサム拒否後に1.3TBデータ漏洩開始](../articles/2026-06-17-novo-nordisk-fulcrumsec-ransomware.md)
