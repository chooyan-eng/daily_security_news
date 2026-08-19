# AirDropとQuick Shareに複数の脆弱性、近接攻撃者がクラッシュやチェック回避を実行可能

- **日付**: 2026-06-30
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/airdrop-and-quick-share-let.html)
- **トピック**: [AirDrop・Quick Share 近接共有プロトコル脆弱性（2026年）](../topics/airdrop-quickshare-vulnerabilities-2026.md)
- **分類**: 新規

## 概要

CISPAヘルムホルツ情報セキュリティセンターの研究者2名が、AppleのAirDropとGoogle/SamsungのQuick Share（近接無線ファイル共有プロトコル）に計6件の脆弱性を発見した。無線到達範囲内の攻撃者が事前接続なしにMac・iPhoneの共有サービスをクラッシュさせたり、Quick Shareのセッションチェックを回避したりできる。推定50億台規模のデバイスに影響する。

## 詳細

### 発見の経緯

研究者Arash Ale EbrahimとNils Ole Tippenhauer（CISPA）は、AirDropとQuick Shareの両プロトコルスタックを発見層の上、すなわちセッション処理・パース処理・信頼判断のレイヤーで横並びに比較分析した初の研究を発表した。

### AirDropの脆弱性

最も影響範囲が広いのは、Foundationフレームワークの XML property list パーサーに存在するスタックオーバーフロー。約200階層のネストを持つ小さなファイルを送りつけるだけでトリガーでき、ラップトップ1台と無線到達範囲があれば、タップや確認プロンプトなしに「全員から受信」設定のMacやiPhoneの共有サービスをクラッシュさせられる。同じパーサー経路はmacOS・iOS・watchOS・tvOS・visionOS上の他のAppleアプリにも影響しうる。

### Quick Shareの脆弱性

SamsungのセッションチェックをバイパスできるQuick Shareの脆弱性に加え、Google製Quick Share Windowsクライアントには競合する接続間のレースコンディションに起因するuse-after-free（解放済みメモリ使用）の脆弱性も発見された。

### 対応状況

Appleは2026年6月29日にリリースしたiOS/macOS 26.5.2で修正を提供済み。GoogleもWindows向けQuick Shareクライアントの修正を提供している。

### 推奨対応

- AirDropの受信設定を「全員」ではなく「連絡先のみ」または「受信しない」に変更
- iOS/macOSを26.5.2以降に更新
- Quick Shareは受信時以外「全員に表示」を避け、Windows版アプリを最新版に更新

---

## 関連記事

（新規トピックのため関連記事なし）
