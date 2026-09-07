# SonicWall、オンプレ版Network Security Managerに複数の重大脆弱性を修正

- **日付**: 2026-09-05
- **出典**: [TheHackerWire](https://www.thehackerwire.com/sonicwall-nsm-on-prem-rce-via-os-command-injection-cve-2026-78327/)
- **トピック**: [SonicWall Network Security Manager (NSM) On-Prem 重大脆弱性群（2026年9月）](../topics/sonicwall-nsm-onprem-cve-2026-78327.md)
- **分類**: 新規

## 概要

SonicWallは2026年9月4日、統合ネットワーク管理製品「Network Security Manager (NSM) On-Prem」（バージョン4.3.0以下）に存在する複数の重大脆弱性を修正するアップデート版4.3.1-R4を公開した。OSコマンドインジェクション（CVE-2026-78327、CVSS9.1）、認可制御の欠落による権限昇格（CVE-2026-78328）、Zip Slip（CVE-2026-81939、CVSS9.1）が含まれる。

## 詳細

CVE-2026-78327は、NSM On-Premの管理インターフェースに存在するOSコマンドインジェクションの脆弱性。SuperAdmin権限を持つ認証済み攻撃者が、管理インターフェース経由で任意のOSコマンドを注入でき、基盤となるホスト上でのリモートコード実行につながる。CVSSスコアは9.1（Critical）。

CVE-2026-78328は認可制御の欠落（Missing Authorization）に分類される脆弱性で、本来SuperAdminのみに許可されるべき操作を、より権限の低いAdminユーザーが実行できてしまい、権限昇格につながる。CVE-2026-81939はZip Slip脆弱性で、細工されたアーカイブファイルをアップロードすることで、本来展開されるべきディレクトリの外部にファイルを書き込める。これによりWebシェルの設置や既存ファイルの上書きなど、更なる侵害につながる可能性がある。

これらの脆弱性は、いずれもNSM On-Prem（オンプレミス版）4.3.0以前に影響し、SonicWallはバージョン4.3.1-R4での修正を提供している。同時期にSonicWallは、SMA1000シリーズの実悪用中ゼロデイ（CVE-2026-83548、CVE-2026-83549、CISAのKEVカタログにも追加）についても対応を進めており、同社製品全体でのセキュリティ対応が続いている。NSMは複数のSonicWallファイアウォールを一元管理するための製品であり、侵害された場合は管理下にある全ファイアウォールに影響が波及するリスクがあるため、管理者には速やかなアップデート適用が強く推奨される。
