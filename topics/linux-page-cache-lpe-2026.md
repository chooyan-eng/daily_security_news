# Linuxカーネルpage cache LPE脆弱性シリーズ（CVE-2026-46331 / CVE-2026-43503）

## 概要

2026年6月、Linuxカーネルのpage cacheメモリを標的とした2つの独立したローカル権限昇格（LPE）脆弱性が相次いで公開・悪用が確認された。

- **CVE-2026-46331**（pedit COW）: トラフィック制御サブシステム `tc` の `act_pedit` モジュールにおける部分的なコピーオンライト（COW）の失敗。CVE割り当て翌日に公開PoC `packet_edit_meme` がGitHubに登場。
- **CVE-2026-43503**（DirtyClone）: ネットワークスタックのソケットバッファ（skb）管理とXFRM/IPsec暗号変換の組み合わせによるpage cache破壊。攻撃痕跡を一切残さないステルス性が特徴。2026年6月25日にJFRogが初の公開エクスプロイトウォークスルーを公開。

両脆弱性ともにユーザー名前空間を通じた非特権ユーザーによるroot権限昇格が可能で、マルチテナントクラウド・Kubernetes環境に特に深刻なリスクをもたらす。

**同一性の判断に役立つ情報：**
- CVE-2026-46331: act_pedit COW / CVSS 未公表（High相当）/ PoC公開: 2026年6月17日
- CVE-2026-43503: DirtyClone / CVSS 8.8 / PoC公開: 2026年6月25日（JFrog）
- 共通攻撃ベクタ: ユーザー名前空間 + page cache破壊 → 特権バイナリ書き換え → rootシェル
- 影響: RHEL 8/9/10、AlmaLinux 8、Debian 11/12/13、Ubuntu
- 修正: v7.1-rc5（CVE-2026-43503）、各ディストリビューションのバックポートパッチ（CVE-2026-46331）

## タイムライン

- [2026-06-27 DirtyClone（CVE-2026-43503）：JFrogがLinuxカーネルソケットバッファLPEのエクスプロイト解析を公開](../articles/2026-06-27-linux-cve-2026-43503-dirtyclone-lpe.md)
- [2026-06-27 Linux CVE-2026-46331「pedit COW」：ネットワーク制御サブシステムのpage cacheメモリ破壊によるroot権限昇格](../articles/2026-06-27-linux-cve-2026-46331-pedit-cow-lpe.md)
