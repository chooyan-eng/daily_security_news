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
- CVE：CVE-2026-43503
- CVSS：8.8（High）
- 脆弱性ファミリー：DirtyFrag
- 発見・PoC：JFrog Security Research（2026年6月25日公開）
- 影響関数：`__pskb_copy_fclone()` / `SKBFL_SHARED_FRAG` フラグ
- 攻撃条件：CAP_NET_ADMIN ケーパビリティ（ユーザー名前空間有効時に非特権ユーザーが取得可能）
- 影響ディストリビューション：Debian・Ubuntu・Fedora（動作確認済み）
- アップストリームパッチ：v7.1-rc5（2026年5月21日、コミット 9e171fc1d7d7）
- CVE: CVE-2026-43503
- CVSS: 8.8（High）
- 脆弱性名: DirtyClone（DirtyFrag ファミリー）
- 発見者: JFrog Security Research
- PoC 公開日: 2026年6月25日
- 影響OS: Linux（Debian, Ubuntu, Fedora 等）
- 前提条件: ローカルユーザー権限 + ドメインネームスペース（デフォルト設定）
- パッチ: Linux v7.1-rc5（コミット 48f6a5356a33、2026年5月24日）
- 通称: DirtyClone
- CVSSスコア: 8.8（High）
- 脆弱性ファミリー: DirtyFrag（DirtyFrag、Fragnesia、DirtyClone）
- PoC公開: JFrog Security Research（2026年6月25日）
- 影響ディストリビューション: Debian、Ubuntu、Fedora（デフォルト設定で確認済み）
- 修正済みカーネル: v7.1-rc5（コミット 9e171fc1d7d7）
- 緩和策: CAP_NET_ADMIN ブロック、esp4/esp6/rxrpc モジュールのブラックリスト登録
- CVE: CVE-2026-46331
- 通称: pedit COW
- 対象コンポーネント: Linux tc サブシステムの `act_pedit` アクション
- 公開エクスプロイト名: packet_edit_meme（2026年6月17日登場）
- 影響ディストリビューション: RHEL 8/9/10、Debian 11/12/13、Ubuntu 18.04〜26.04
- 修正方法: ベンダー提供の修正済みカーネルを適用後リブート
- 必要な権限: 非特権ユーザー名前空間内の CAP_NET_ADMIN（デフォルト設定で取得可能）

## タイムライン

- [2026-06-29 Linux CVE-2026-46331 pedit COW — tc サブシステムの OOB 書き込みで非特権ユーザーがroot昇格](../articles/2026-06-29-linux-pedit-cow-cve-2026-46331.md)
- [2026-06-29 Linux CVE-2026-43503 DirtyClone — JFrogがPoCを公開、DirtyFrag系列の新たな権限昇格脆弱性](../articles/2026-06-29-linux-dirtyclone-cve-2026-43503.md)
- [2026-06-27 DirtyClone（CVE-2026-43503）：Linuxカーネルの特権昇格、痕跡なしでルート奪取のPoC公開](../articles/2026-06-28-dirtyclone-linux-cve-2026-43503.md)
- [2026-06-27 Linux CVE-2026-46331「pedit COW」：ネットワーク制御サブシステムのpage cacheメモリ破壊によるroot権限昇格](../articles/2026-06-27-linux-cve-2026-46331-pedit-cow-lpe.md)
- [2026-06-27 DirtyClone（CVE-2026-43503）：JFrogがLinuxカーネルソケットバッファLPEのエクスプロイト解析を公開](../articles/2026-06-27-linux-cve-2026-43503-dirtyclone-lpe.md)
- [2026-06-26 DirtyClone (CVE-2026-43503)：Linux カーネル特権昇格 PoC 公開](../articles/2026-06-26-dirtyclone-linux-kernel-cve-2026-43503.md)
