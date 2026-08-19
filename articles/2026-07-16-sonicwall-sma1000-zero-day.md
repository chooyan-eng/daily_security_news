# SonicWall SMA1000シリーズにゼロデイ脆弱性2件、連鎖悪用で認証情報・MFAシード窃取

- **日付**: 2026-07-16
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/sonicwall-warns-of-sma1000-flaws-exploited-in-zero-day-attacks-patch-now/), [The Hacker News](https://thehackernews.com/2026/07/two-sonicwall-sma-1000-zero-days.html), [Rapid7](https://www.rapid7.com/blog/post/etr-rapid7-mdr-team-discovers-new-sonicwall-sma1000-zero-days-being-actively-exploited-cve-2026-15409-cve-2026-15410/)
- **分類**: 新規

## 概要

SonicWallのリモートアクセス製品SMA1000シリーズ（SMA6210・SMA7210・SMA8200v）に2件のゼロデイ脆弱性（CVE-2026-15409、CVE-2026-15410）が存在し、攻撃者が両者を連鎖させて実際に悪用していることが判明。CISAはBOD 26-04に基づき米連邦機関に2026年7月17日までの対応を義務付けた。

## 詳細

Rapid7 MDRチームが発見し、SonicWallが2026年7月14日に公表した。CVE-2026-15409はSMA1000のWork Placeインターフェースに存在するサーバーサイドリクエストフォージェリ（SSRF）脆弱性で、CVSSスコアは最大値の10.0。未認証のリモート攻撃者がアプライアンスに任意の宛先へのリクエストを強制させることができる。

CVE-2026-15410はSMA1000の管理コンソールに存在する認証後のコードインジェクション脆弱性（CVSS 7.2）で、リモートの認証済み管理者が任意のOSコマンドを実行できる。SonicWallは複数のインシデントを調査した結果、両脆弱性が実際に悪用されていることを確認しており、攻撃者はまずCVE-2026-15409のSSRFで初期アクセスを得たのち、CVE-2026-15410のコードインジェクションと連鎖させてアプライアンスを完全に制御する手口をとっているとみられる。

侵害後、攻撃者は高価値な認証情報、アクティブセッションデータベース、TOTP多要素認証のシード設定を窃取しており、これにより長期的な永続アクセスを確保する意図があると分析されている。ステルス性の高い初期アクセス手段として悪用されている点が特徴で、リモートアクセス基盤（VPN/SMA）を狙った攻撃が引き続き活発であることを示す事例。SonicWallはパッチの適用と、侵害の兆候が見られる場合の認証情報・MFAシードのローテーションを強く推奨している。
