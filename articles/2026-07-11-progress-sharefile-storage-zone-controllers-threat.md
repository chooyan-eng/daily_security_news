# Progress Software、ShareFile Storage Zone Controllersの「信頼性の高い脅威」を理由に緊急シャットダウンを要請

- **日付**: 2026-07-11
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/progress-urges-sharefile-customers-to-shut-down-servers-over-credible-threat/), [The Hacker News](https://thehackernews.com/2026/07/urgent-progress-tells-sharefile.html)
- **トピック**: [Progress ShareFile Storage Zone Controllers 緊急セキュリティ脅威（2026年7月）](../topics/progress-sharefile-storage-zone-controllers-2026.md)
- **分類**: 新規

## 概要

Progress Softwareは2026年7月10日、企業向けファイル共有製品ShareFileのオンプレミス構成部品「Storage Zone Controllers」を狙う「信頼性の高い外部からの脅威」を検知したとして、利用顧客に対しWindowsサーバーの手動シャットダウンを緊急要請した。現時点でアカウントやデータへの不正アクセスの証拠はないとされるが、脆弱性の詳細（ゼロデイか既知の脆弱性かを含む）は未公表。

## 詳細

ShareFile Storage Zone Controllersは、企業がファイルを自社オンプレミスのWindowsサーバー上に保持しつつ、認証・ユーザー管理・共有・コラボレーション機能はShareFileのクラウドプラットフォームを利用できるようにするコンポーネントである。多くの企業がコンプライアンス要件からファイルを自社管理下に置くためにこの構成を採用している。

Progressは顧客向けメールで「Progress SoftwareのShareFile Storage Zone Controllersを標的とした信頼性の高い外部からの脅威が存在すると考える根拠がある」と説明し、予防的措置としてStorage Zone Controllersを利用するShareFileアカウントへのアクセスを一時的に無効化したことを明らかにした。その上で「Storage Zone Controllersをホストしているサーバーを手動でシャットダウンする必要がある。これはデータの安全を確保するための重要な追加ステップである」と顧客に指示している。

同社は社内外のサイバーセキュリティ専門家と協力して脅威の調査を進めているとしつつ、脅威がゼロデイ脆弱性の悪用によるものか、既知の脆弱性を突いたものかは明らかにしていない。また、実際に侵害されたStorage Zone Controllersが存在するかどうかについても言及を避けている。Progressは24時間以内に追加情報を提供するとしている。

ShareFileはCitrix(現Cloud Software Group)系列のファイル共有・コラボレーションサービスとして金融、医療、法律分野など機密性の高いファイルを扱う企業に広く利用されており、オンプレミスコンポーネントが標的となった場合、大規模な情報漏洩や侵入の足がかりとなるリスクがある。過去にもCitrix ShareFile Storage Zones Controllerでは深刻な脆弱性（CVE-2023-24489など）が発見されており、同種製品は繰り返し攻撃対象となってきた経緯がある。

## 対策・推奨事項

- Storage Zone Controllersをホストするサーバーを、Progressの指示に従い直ちにシャットダウンする
- Progressからの追加アドバイザリを注視し、パッチ公開後は速やかに適用する
- ネットワークログを確認し、Storage Zone Controller関連の不審な通信がないか調査する

---

## 関連記事

なし
