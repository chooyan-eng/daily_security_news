# Check Point、VPN証明書処理に起因するCVSS 9.8の重大脆弱性2件を公表

- **日付**: 2026-09-10
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/check-point-discloses-two-98-rated-vpn.html), [Cyber Security News](https://cybersecuritynews.com/check-point-vpn-vulnerabilities/)
- **トピック**: なし（新規事案）
- **分類**: 新規

## 概要

Check Point Softwareは、同社のVPN製品における証明書処理に起因する2件の重大な脆弱性CVE-2026-85102・CVE-2026-85103（いずれもCVSS 9.8）を公表し、修正パッチを提供した。特定条件下で未認証のリモートコード実行につながる可能性があるが、同社は現時点で実悪用や公開エクスプロイトコードの確認はないとしている。

## 詳細

CVE-2026-85102は、VPNネゴシエーション時における証明書の信頼性検証不備（CWE-295）に起因する脆弱性である。提示された証明書の信頼性を適切に検証しないため、未認証の攻撃者がVPNネゴシエーションを不正に進行させ、Security Gateway上で任意のコードを実行できる可能性がある。リモートアクセスVPN・拠点間VPNの双方の構成に影響する。

CVE-2026-85103は、VPN証明書のASN.1構造を解析する処理に存在するヒープベースのバッファオーバーフロー(CWE-122)である。攻撃者は悪意のある証明書を送信するだけでこのオーバーフローを引き起こすことができ、Quantum Security GatewayおよびQuantum Security Management双方でコード実行に至る可能性がある。

両脆弱性は、R81.20・R82・R82.10系列でJumbo Hotfix Takeが修正版未満のバージョン、およびR80.40・R81など複数のサポート終了バージョンを含む、Check Point Security Gateway、Security Management Server、Sparkファイアウォールの幅広い展開構成に影響する。最新のR82.20は影響を受けないことが確認されている。

いずれの脆弱性もCheck Point自社の研究チームが内部調査で発見したものであり、同社は現時点で実際の悪用や公開されたPoCコードの存在は確認していないとしている。ただし、CVSS 9.8という深刻度と、VPNゲートウェイという境界防御の要となる機器が対象であることから、対象顧客には速やかなパッチ適用が強く推奨されている。
