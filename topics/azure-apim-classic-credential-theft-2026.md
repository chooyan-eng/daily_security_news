# Azure API Management Classic 脆弱性悪用・API認証情報窃取（2026年11月）

## 概要

Azure API Management の Classic ティアの脆弱性が悪用され、保存されたAPI認証情報・named valuesが窃取された事案。ノルウェーのEquinor、Skagerak Energi等が被害。Microsoftは2026年11月19日に修正（v2ティアは影響なし）。修正前に窃取された認証情報は有効なため全シークレットのローテーションが必要。修正済みランタイムは 0.52.31936 以上／0.53.31938 以上。CVE番号は未確認。

## タイムライン

- [2026-11-24 Azure API Management（Classic）の脆弱性が悪用されAPI認証情報が窃取、ノルウェーのエネルギー企業に被害](../articles/2026-11-24-azure-apim-classic-credential-theft.md)
