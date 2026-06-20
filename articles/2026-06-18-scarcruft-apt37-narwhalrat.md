# 北朝鮮 APT37（ScarCruft）、偽 Microsoft セキュリティ通知で NarwhalRAT マルウェアを配布

- **日付**: 2026-06-18
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/fake-microsoft-alerts-used-to-deploy.html), [GBHackers](https://gbhackers.com/apt37-hackers-use-narwhalrat-malware/), [SC Media](https://www.scworld.com/brief/north-korean-hackers-use-fake-microsoft-alerts-to-deploy-narwhalrat-malware)
- **トピック**: [北朝鮮 APT37（ScarCruft）NarwhalRAT スピアフィッシングキャンペーン（2026年6月）](../topics/scarcruft-apt37-narwhalrat-2026.md)
- **分類**: 新規

## 概要

北朝鮮の国家支援型ハッカーグループ ScarCruft（APT37）が、Microsoft アカウントセキュリティ通知を偽装したスピアフィッシングメールで新型マルウェア「NarwhalRAT」を配布するキャンペーンを展開している。従来の主力マルウェア RokRAT からの転換として注目されており、韓国を主な標的とする。キーロギング・スクリーンショット・音声録音などの機能を持ち、pCloud や韓国系ウェブサイトを C2 チャネルとして使用する。

## 詳細

### キャンペーンの概要

2026年6月16日に公開された分析によると、ScarCruft は Microsoft 365 のセキュリティアラートを偽装したスピアフィッシングメールを使用して NarwhalRAT をターゲット組織に送り込んでいる。

### 攻撃の手口

1. **誘導メール**: Microsoft アカウントセキュリティ警告を模した本文で、アカウントへの疑わしいアクセスや OTP 乱用の懸念を煽る内容
2. **添付ファイル**: HWP ドキュメントに偽装した実際は ZIP アーカイブ（悪意ある LNK ファイルを含む）
3. **実行**: ZIP を展開して LNK ファイルをダブルクリックすることでマルウェアが起動
4. **感染**: 多段階のインメモリ感染チェーンを経て NarwhalRAT が実行される

### NarwhalRAT の機能

NarwhalRAT は以下の機能を持つフル機能の RAT（Remote Access Trojan）：
- **キーロギング**: 入力されたすべてのキーストロークを記録
- **スクリーンショット**: 定期的な画面キャプチャ
- **音声録音**: マイクからの音声収集
- **システム情報収集**: デバイス情報・インストール済みソフトウェア・ネットワーク設定
- **ファイル操作**: ファイルのアップロード・ダウンロード・実行

### C2 インフラ

NarwhalRAT は独自の C2 サーバーの代わりに「デッドドロップ」方式を採用：
- **pCloud**: クラウドストレージを C2 通信チャネルとして使用
- **韓国系ウェブサイト**: 韓国語圏のウェブサービスを C2 チャネルとして利用

このデッドドロップ方式により、セキュリティ製品による C2 通信の検知が困難になっている。

### RokRAT からの転換の意義

ScarCruft の主力マルウェアはこれまで RokRAT だったが、NarwhalRAT の使用は新しい機能・インフラを持つマルウェアへの転換を示す。このアップデートは、RokRAT の TTPs（戦術・技術・手順）が広く知られたことへの対応と見られる。

### 想定されるターゲット

Microsoft 365 を業務で使用するすべての組織が潜在的なターゲット。特に：
- 韓国政府・防衛関連組織
- 韓国のシンクタンク・研究機関
- 北朝鮮の政策に関与する非政府組織（NGO）
- 韓国企業（特に防衛・IT・エネルギーセクター）

### 推奨対応

1. Microsoft からのセキュリティアラートメールの添付ファイルは絶対に開かない（Microsoft は添付ファイルでセキュリティ通知を送付しない）
2. LNK ファイルの実行を制限するポリシーを設定（Windows Group Policy）
3. 従業員向けのスピアフィッシング訓練を実施
4. EDR/XDR ソリューションでインメモリ実行の検知を強化
5. pCloud 等のクラウドストレージへの異常な通信を監視

---

## 関連記事
