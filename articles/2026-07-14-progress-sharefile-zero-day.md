# Progress、ShareFile Storage Zone Controller のゼロデイ脆弱性にパッチを提供し稼働停止指示を解除

- **日付**: 2026-07-14
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/progress-confirms-sharefile-zero-day-flaw-behind-storage-zone-shutdown/)
- **トピック**: [Progress ShareFile Storage Zone Controllers 緊急セキュリティ脅威（2026年7月）](../topics/progress-sharefile-storage-zone-controllers-2026.md)
- **分類**: 続報
## 概要

Progress Software は2026年7月10日、ファイル共有サービス ShareFile の「Storage Zone Controller」に対する信頼性の高い外部脅威を検知し、全顧客に稼働サーバーの緊急停止を指示した。調査の結果、5.x/6.x系全バージョンに影響するパストラバーサル脆弱性が判明。7月14日、パッチ版の提供により停止指示を解除した。

## 詳細

### 経緯

Progress Software は2026年7月10日、ファイル共有・コラボレーションサービス ShareFile のオンプレミスコンポーネント「Storage Zone Controller」について「信頼性の高い外部からのセキュリティ脅威」を確認したとして、全顧客に対し当該コンポーネントを稼働させる Windows サーバーの即時停止を指示した。この時点ではパッチは提供されておらず、稼働停止が唯一の緩和策とされた。

### 脆弱性の内容

調査の結果、原因は Storage Zone Controller の 5.x および 6.x 系バージョン全てに影響するパストラバーサル脆弱性であることが判明した。認証済みの管理者ユーザーが、アプリケーションのサービスアカウントがアクセス可能な任意のファイルを読み取ったり、攻撃者が制御するコンテンツを任意のディレクトリに書き込んだり、サーバーのファイルシステム構成を列挙したりすることが可能だった。CVE番号は予約済みだが、公開は2週間後を予定している。

### 復旧

Progress は2026年7月14日、パッチ版となる ShareFile Storage Zone Controller バージョン 5.12.5 および 6.0.2 をリリースし、パッチ適用済みのコントローラーから順次稼働を再開できるようにした。同社は全顧客に速やかなアップデート適用を強く推奨している。

### 影響の有無

Progress は現時点で、いかなる顧客アカウントやデータへの不正アクセスの証拠も確認しておらず、能動的な脅威も特定していないと説明している。

### 技術的補足

ShareFile のようなエンタープライズ向けファイル共有・コラボレーションWebアプリケーションは、大量の機密ファイルを取り扱う性質上、パストラバーサル脆弱性が発見された場合の潜在的被害が大きい。今回、ベンダーがCVE公開前に「稼働停止」という異例の緩和策を指示した点は、脆弱性の深刻度と外部からの実際の脅威情報の存在を示唆している。

---

## 関連記事

なし（新規トピック）
