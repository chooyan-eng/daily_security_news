# Ubiquiti、UniFi Connect/Talk/Access/Protect/OS に複数の最大深刻度脆弱性を公表・修正

- **日付**: 2026-07-09
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/ubiquiti-patches-critical-unifi-flaws.html)
- **トピック**: [Ubiquiti UniFi OS 最大深刻度脆弱性の悪用（2026年6月）](../topics/ubiquiti-unifi-os-vulnerabilities-2026.md)
- **分類**: 関連

## 概要

Ubiquitiは2026年7月8日、UniFi Connect・Talk・Access・Protect・OSにまたがる複数の重大脆弱性を修正するアップデートを公開した。最大深刻度（CVSS 10.0）のCVE-2026-50746をはじめ、CVSS 9.9の脆弱性が3件確認されている。現時点で実悪用の証拠は報告されていないが、認証不要または低権限からの権限昇格・任意コマンド実行が可能とされ、6月に発覚したUniFi OS Serverの脆弱性群とは別のCVE群である。

## 詳細

Ubiquitiが公開したSecurity Advisory Bulletin 066では、UniFi製品群にまたがる複数の脆弱性が報告されている。最も深刻なのはCVE-2026-50746（CVSS 10.0）で、UniFi Connect Application 3.4.16以前に存在する不適切なアクセス制御の欠陥により、ネットワーク隣接の攻撃者が認証なしでコマンドインジェクションを実行できる。

CVE-2026-50747（CVSS 9.9）はUniFi Talkにおける認証済みSQLインジェクションで、低権限のネットワークユーザーがデータベースを操作できる。CVE-2026-50748（CVSS 9.9）はUniFi Accessにおけるコマンドインジェクションで、同様に低権限ユーザーからの完全な権限奪取につながる。さらにCVE-2026-55115（CVSS 9.9）はUniFi Protect ApplicationにおけるSSRF（サーバーサイドリクエストフォージェリ）で、ネットワークアクセス権を持つ低権限攻撃者がホストデバイス上で権限昇格を行うことを可能にする。

Ubiquitiによれば、これらの脆弱性を悪用するには基本的にネットワークへのアクセス（一部は認証不要）が必要であり、インターネットから直接到達可能なケースは限定的とみられるが、UniFi機器は企業・教育機関のネットワーク管理基盤として広く使われているため影響範囲は大きい。

推奨されるアップデートは以下の通り：UniFi Connectは3.4.20以降、Talkは5.2.2以降、Accessは4.2.29以降、Network Applicationは10.4.57以降、Protectは7.1.83以降、Protect Floodlightは1.13.6以降、UDM/UNVR/UNAS等のUniFi OSは5.1.19以降。

なお、本件は2026年6月に発覚しCISA KEVに追加されたUniFi OS Serverの脆弱性群（CVE-2026-34908/34909/34910、アクセス制御・パストラバーサル・コマンドインジェクションの連鎖によるroot RCE）とはCVEが異なる別の脆弱性群であり、現時点で積極的悪用の報告もない点が異なる。ただし同一ベンダー・同一製品ファミリーにおいて短期間で複数の重大脆弱性が発覚している点は注視が必要である。

---

## 関連記事

- [Ubiquiti UniFi OS 最大深刻度の3脆弱性が積極悪用 - 大学・高等教育機関を主要標的に](../articles/2026-06-20-ubiquiti-unifi-os-max-severity-exploit.md) - 同一製品ファミリー（UniFi OS）における2026年6月の別の重大脆弱性・積極悪用事案
