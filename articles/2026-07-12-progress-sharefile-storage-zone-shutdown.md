# Progress、ShareFile Storage Zone Controllers 利用企業に「信頼性の高い脅威」を理由に緊急サーバー停止を要請

- **日付**: 2026-07-12
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/urgent-progress-tells-sharefile.html)
- **トピック**: [Progress ShareFile Storage Zone Controllers 緊急停止要請（2026年7月）](../topics/progress-sharefile-storage-zone-2026.md)
- **分類**: 新規

## 概要

Progress Softwareは、オンプレミス版ファイル共有製品「ShareFile」のコンポーネント「Storage Zone Controllers」の利用企業に対し、「信頼性の高い外部からの脅威」を確認したとして、対象サーバーの即時停止を求めるメールを送付した。CVE番号や脅威の詳細は非公開だが、ゼロデイの可能性を含め警戒されている。

## 詳細

### 何が起きたか

2026年7月10日、Progress SoftwareはShareFile Storage Zone Controllersを利用する顧客に対し、該当のWindowsサーバーを直ちにシャットダウンするよう求める緊急連絡を行った。Storage Zone Controllersは、ファイルの実体を顧客管理下のインフラに保持しながら、認証・管理・共有・コラボレーション機能をShareFileクラウド側で提供するオンプレミス連携コンポーネントである。

Progressは「信頼性の高い外部からの脅威（credible external security threat）」を識別したと説明しているが、脅威の技術的な性質（ゼロデイか既知の脆弱性か）、CVE番号、実際に侵害が発生した組織の有無については本稿執筆時点で公表していない。

### 影響範囲

今回の警告はオンプレミスのStorage Zone Controllersを利用する環境が対象であり、クラウドのみで完結するShareFile環境が影響を受けるとの言及はない。Progressは、ShareFileアカウントやデータへの不正アクセスを示す兆候は現時点で確認していないとしつつも、内部および外部のセキュリティ専門家と共に脅威の評価を進めるための予防的措置として、サーバー停止という異例の強い対応を取ったとしている。

### 今後の見通し

Progressは24時間以内に追加情報を共有する見込みだと表明した。同社を巡っては過去にもMOVEit Transferの大規模なゼロデイ悪用（Cl0pランサムウェアグループによる）の前例があり、ファイル共有製品が高価値標的となりやすいことから、業界全体で今回の動向が注視されている。

### 推奨対応

Storage Zone Controllersを稼働させている組織は、Progressからの公式通知に従い、対象サーバーの停止を検討するとともに、関連ログの保全・監視強化を行うことが推奨される。

---

## 関連記事

（新規トピックのため関連記事なし）
