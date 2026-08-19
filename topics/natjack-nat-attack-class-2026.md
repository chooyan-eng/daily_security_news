# NatJack – NAT実装の設計的脆弱性による攻撃クラス（2026年）

## 概要

研究者Malcolm StaggがBlack Hatで発表した新攻撃クラス「NatJack」。NATの接続状態管理を操作してTCPセッション乗っ取り、DNSスプーフィング、マップされたポートの露出、NATテーブル枯渇を引き起こす。13ベンダー・32製品を対象に調査し、テストしたすべての実装が何らかの手法に対して脆弱と判明。Windows Hyper-V NAT（CVE-2026-56181）とLinux Netfilter conntrack（CVE-2026-63913）に個別CVEが割り当てられている。攻撃には同一NAT配下への足がかりが必要で、2026年8月7日時点で実際の悪用の公開証拠はない。

**同一性の判断に役立つ情報：**
- 攻撃名: NatJack
- 発見者: Malcolm Stagg
- CVE: CVE-2026-56181（Windows NAT/Hyper-V）、CVE-2026-63913（Linux Netfilter conntrack）
- 対象範囲: NAT実装全般（32製品・13ベンダーで検証）
- 発表: Black Hat 2026

## タイムライン

- [2026-08-07 新種攻撃クラス「NatJack」– NATのテーブル操作でTCPセッション乗っ取り・DNSスプーフィングが可能に](../articles/2026-08-07-natjack-nat-attack-class.md)
