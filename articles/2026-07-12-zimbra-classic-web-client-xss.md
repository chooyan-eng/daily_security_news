# Zimbra、Classic Web Client の重大な保存型XSS脆弱性に対するパッチ適用を呼びかけ

- **日付**: 2026-07-12
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/zimbra-urges-customers-to-patch-critical-web-client-xss-flaw/)
- **トピック**: [Zimbra Classic Web Client 保存型XSS脆弱性（2026年）](../topics/zimbra-classic-web-client-xss-2026.md)
- **分類**: 新規

## 概要

Zimbra Collaboration Suite の Classic Web Client に、細工されたメールの閲覧だけでセッション乗っ取りなどにつながる保存型クロスサイトスクリプティング（XSS）の重大な脆弱性が発見された。Google Threat Analysis Group（TAG）が報告し、Zimbraは7月7日に修正版10.1.19をリリースした。国家支援型攻撃者による標的化の実績を持つ製品であることから警戒が呼びかけられている。

## 詳細

### 脆弱性の内容

Zimbra Classic Web Client には保存型XSSの脆弱性が存在し、攻撃者が特別に細工したメールをユーザーに送りつけ、それを開かせるだけで、被害者のウェブメールセッション内で任意のJavaScriptコードを実行できる。これにより、セッションクッキーやトークンの窃取、メールボックス内容の閲覧・持ち出し、アカウント設定の改変などが可能になるとみられる。

現時点でCVE番号は割り当てられていないが、深刻度は「重大（Critical）」と評価されている。

### 発見の経緯

この脆弱性はGoogleの脅威分析チーム（TAG）によって報告された。TAGは国家支援型ハッカーによるゼロデイ悪用を追跡する部門であり、同チームからの報告であること自体が、既に標的型攻撃での悪用可能性を示唆する材料として注目されている。

### 対応状況

Zimbraは2026年7月7日、修正済みパッケージ（zimbra-patch および zimbra-mbox-webclient-war）を含むバージョン10.1.19をリリースした。7月11日時点で、実際の悪用が確認されたとの報告はないが、Zimbra製品はこれまでWinter VivernやAPT29といったロシア系国家支援ハッカーによって繰り返し標的にされ、政府機関や軍事関係組織からの認証情報・メール窃取に悪用されてきた経緯がある。

### 推奨対応

Zimbraを利用する組織に対しては、Classic Web Clientを稼働させている全インスタンスの速やかな10.1.19へのアップデートが強く推奨されている。特に政府機関・軍事関連組織など高価値標的となりやすい組織は優先的な対応が求められる。

---

## 関連記事

（新規トピックのため関連記事なし）
