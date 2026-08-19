# 新種攻撃クラス「NatJack」– NATのテーブル操作でTCPセッション乗っ取り・DNSスプーフィングが可能に

- **日付**: 2026-08-07
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/new-natjack-attacks-hijack-tcp-sessions.html) / [Network World](https://www.networkworld.com/article/4206287/natjack-exploits-put-nat-security-assumptions-to-the-test-at-black-hat.html)
- **トピック**: [NatJack – NAT実装の設計的脆弱性による攻撃クラス（2026年）](../topics/natjack-nat-attack-class-2026.md)
- **分類**: 新規

## 概要

セキュリティ研究者Malcolm StaggがBlack Hatで発表した新攻撃クラス「NatJack」は、NAT（ネットワークアドレス変換）の接続状態管理を操作し、アクティブなTCPセッションの乗っ取り、DNSレスポンスの偽装、マップされたポートの露出、NATテーブルの枯渇を可能にする。Windows（Hyper-V NAT、CVE-2026-56181）とLinux（Netfilter conntrack、CVE-2026-63913）に固有のCVEが割り当てられ、テストした32製品すべてで何らかのNatJack手法が有効だった。

## 詳細

### 概要

NatJackは、独立して開発された複数のNAT実装に共通する設計上の弱点を突く攻撃手法群である。攻撃者は同一NAT配下（同じルーターやゲートウェイの内側）にいる必要があり、他のホストのTCPセッションの状態を推測・操作することで、セッションハイジャック、DNSスプーフィング、内部ポートマッピングの露出、NATテーブル枯渇によるサービス妨害を引き起こせる。

研究では13ベンダーに通知し、32製品・構成、95件のレポートにわたってテストが実施された。その結果、テストされたすべての実装が何らかの形でNatJackの手法に対して脆弱であることが判明した。

### CVEと対象範囲

**CVE-2026-56181**（CVSS 8.3）: Windows NAT（Hyper-Vが使用）に影響。対象は Windows 11 24H2（26100.8875未満）、25H2（26200.8875未満）、26H1（28000.2525未満）、Windows Server 2025（26100.33158未満）。

**CVE-2026-63913**（CVSS 8.2）: Linux Netfilter conntrackに影響。kernel.orgのCNAレコードによれば、細工されたSYNパケットに続けて不正なシーケンス番号を持つRSTパケットを送ることで、conntrackロジックが方向性を検証しないためアクティブなNATエントリが不正に閉鎖状態へ遷移させられる。修正済み安定版: 5.10.259、5.15.210、6.1.176、6.6.143、6.12.93、6.18.35、7.0.12、7.1。

### 悪用状況

The Hacker Newsの報道時点（2026年8月7日）で、NatJack手法が実際の攻撃で悪用されたという公開証拠は確認されていない。

### 対策

1. Windows・Linuxカーネルの該当修正版への更新
2. 信頼できない内部ネットワーク（公衆Wi-Fi、共有オフィスLANなど）でのNAT配下運用リスクの見直し
3. NAT越しのTCPセッションに対する追加的な暗号化・認証（TLS等）の徹底

---

## 関連記事

なし（新規トピック）
