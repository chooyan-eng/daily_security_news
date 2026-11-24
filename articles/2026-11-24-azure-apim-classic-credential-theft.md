# Azure API Management（Classic）の脆弱性が悪用されAPI認証情報が窃取、ノルウェーのエネルギー企業に被害

- **日付**: 2026-11-24
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/11/24/azure-apim-vulnerability-credential-theft/)
- **トピック**: [Azure API Management Classic 脆弱性悪用・API認証情報窃取（2026年11月）](../topics/azure-apim-classic-credential-theft-2026.md)
- **分類**: 新規

## 概要

MicrosoftはAzure API ManagementのClassicティアに存在した脆弱性が悪用され、保存されていたAPI認証情報が窃取されたと明らかにした。ノルウェーのEquinor、Skagerak Energiなどエネルギー企業が影響を受け、NSMは全利用者にシークレットのローテーションを勧告。修正は11月19日に展開済みだが、それ以前に窃取された認証情報は有効なままとなる。

## 詳細

### 概要

- 対象: Azure API Management（APIM）の Classic ティア。v2 ティアは影響なしとMicrosoftは説明。
- 悪用内容: APIMに保存された認証情報（named values、バックエンド接続用のキー／トークン等）の窃取。
- 発見: ノルウェー国家安全保障局（NSM）によれば、同国のエネルギー業界が最初に発見し、他国・他業種にも影響が及んでいる。被害組織としてEquinor、Skagerak Energiが報じられた。
- 修正: Microsoftが11月19日にサービス側で対処。ただし修正は窃取済みの認証情報を無効化しない。
- 影響顧客数は非公表。CVE番号は確認できていない（一部メディアは「CVEなし」「非推奨のレガシーエンドポイントの認証バイパス」と報じるが未検証）。

### 推奨対応（NSM勧告ベース）

- APIMを利用する全組織は、シークレットおよびnamed valuesが侵害された前提で、全トークン・シークレットをローテーションする。
- ランタイムバージョンが 0.52.31936 以上、または 0.53.31938 以上であることを確認する。
- 11月19日以前のバックエンドAPIへのアクセスログを確認し、APIM以外の送信元からの正規キー使用がないか調査する。

### Web/モバイル開発者への示唆

APIMはモバイルアプリやSPAのBFF／APIゲートウェイとして広く使われ、バックエンドの長期キーを集約しがちである。Key Vault参照＋マネージドIDへの移行、バックエンド側でのIP／VNet制限、キーの短寿命化により、ゲートウェイ侵害時の影響を限定できる。

関連報道: [BleepingComputer](https://www.bleepingcomputer.com/news/security/microsoft-azure-flaw-exploited-to-steal-customers-api-credentials/)、[SecurityWeek](https://securityweek.com/azure-flaw-exploited-to-target-secrets-at-norwegian-energy-firms)

> 注: 本セッションでは外部サイトの本文取得ができず（ネットワーク制限）、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事
