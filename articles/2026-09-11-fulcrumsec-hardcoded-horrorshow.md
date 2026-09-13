# FulcrumSec、「Hardcoded Horrorshow」と称しクライアント側JS・モバイルアプリのハードコード認証情報を悪用する手口を継続

- **日付**: 2026-09-11
- **出典**: [MoxFive](https://www.moxfive.com/blog/who-is-fulcrumsec-inside-the-cloud-extortion-group-behind-21-victims-and-counting), [BreachNews](https://breachnews.com/threat-actors/fulcrumsec/)
- **トピック**: [Novo Nordisk FulcrumSec データ窃取・恐喝事件（2026年6月）](../topics/novo-nordisk-fulcrumsec-2026.md)
- **分類**: 続報

## 概要

Novo Nordiskへの大規模データ窃取・恐喝事件を引き起こしたサイバー犯罪グループFulcrumSecが、クライアントサイドJavaScript・モバイルアプリのソースツリー・公開GitHubリポジトリ・デプロイ設定ファイルにハードコードされた認証情報を悪用する手口を「Hardcoded Horrorshow」と称し、継続的に展開していることが明らかになった。

## 詳細

FulcrumSecは2025年9月頃から活動する金銭目的のデータ窃取・恐喝グループで、クラウドにホストされたデータベースの高速な窃取を専門としている。手口の核心は、企業がクライアントサイドJavaScriptやモバイルアプリのソースコード、公開GitHubリポジトリ、デプロイ設定ファイルなどに本番環境用の認証情報（APIキー、アクセストークン等）を誤って埋め込んでしまう基本的なミスを突くというものである。

Novo Nordiskの事案では、クライアントサイドJavaScriptバンドルに埋め込まれたAzureコンテナレジストリの認証情報とGitHub Personal Access Token（PAT）が初期侵入に使われ、同社ネットワーク内に約2カ月間潜伏した後、臨床試験データ・AIモデル・創薬データを含む約1.3TBのデータが窃取された。同グループはNovo Nordiskの担当者が「2つの異なるチーム、2つの異なるアプリケーションで、同じ初歩的なミスを2度犯した」と主張している。

同様の手口による被害はNovo Nordiskにとどまらず、英マンチェスター空港グループ（Manchester Airports Group）、ロンドン拠点のコンサルティング会社Arup Group、シンガポール拠点のGlobal Schools Groupなど、業種・地域を問わず複数の組織に及んでいる。FulcrumSecは年間売上高別にリストアップした8件の「予告標的」も公開しており、その中には売上高最大500億ドル規模の企業も含まれるとされ、今後も同様の手口による被害が継続する可能性が高い。

ローテーションされないAPIキーや誤設定されたクラウド権限の悪用と組み合わさることで、ハードコードされた認証情報の一つの見落としが、クラウドストレージから最大100TB規模のデータ持ち出しにつながり得る点が、本キャンペーンの特徴として強調されている。組織にはクライアントサイドコード・モバイルアプリ・リポジトリ内のシークレットスキャンの徹底が改めて求められる。

---
