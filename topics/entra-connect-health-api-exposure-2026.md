# Microsoft Entra Connect Health API テナントメタデータ不正取得（2026年11月）

## 概要

Microsoft Entra Connect HealthのAPIの欠陥（2026年7月23日混入、11月9日検知、11月19日サービス側修正）が悪用され、テナントID・表示名・初期ドメイン・国コード・ライセンス種別・同期状態・管理者／技術連絡先メールなどのテナントメタデータが不正に読み取られた事案。11月20日に影響テナントへ通知。パスワード・トークン・鍵の流出はなし。CVE番号は未確認。確認用スクリプト: aka.ms/ConnectHealth/scripts。

## タイムライン

- [2026-11-22 Microsoft、Entra Connect Health APIの欠陥悪用によるテナントメタデータの不正取得を公表](../articles/2026-11-22-entra-connect-health-api-flaw.md)
