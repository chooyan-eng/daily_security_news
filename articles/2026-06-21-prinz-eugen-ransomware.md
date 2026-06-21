# Prinz Eugen — 身代金要求書を残さない新興ランサムウェア、最近更新ファイルを優先暗号化

- **日付**: 2026-06-21
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/new-prinz-eugen-ransomware-prioritizes-recent-files-for-encryption/) / [Rescana](https://www.rescana.com/post/prinz-eugen-ransomware-targets-recent-files-and-abuses-remote-management-tools-technical-analysis-and-supply-chain-risks)
- **トピック**: [Prinz Eugen ランサムウェア（2026年6月〜）](../topics/prinz-eugen-ransomware-2026.md)
- **分類**: 新規

## 概要

Malwarebytes の脅威調査チーム Threatdown が新興ランサムウェア「Prinz Eugen」の詳細分析を公開。ランサムノートを一切残さず、暗号化後にアウトオブバンド（メール・ダークウェブポータル等）で被害者に連絡する手口が特徴。最近更新されたファイルを優先して暗号化し、Go 言語実装の ChaCha20-Poly1305 暗号と Argon2id による鍵導出を採用。RaaS モデルは採用していない独立型組織とみられる。

## 詳細

### 概要と攻撃スタイル

Prinz Eugen はハンズオンキーボード型（hands-on-keyboard）の侵害を好む脅威アクターによって運営されており、正規のリモート監視・管理（RMM）ツールやLOLBAS手法を組み合わせる。

### 侵害の流れ

1. **初期アクセス**: 盗まれた RDP 認証情報を使用してシステムに侵入
2. **ラテラルムーブメント**: RMM ツール（AnyDesk、TeamViewer 等の正規ソフト）を使ってネットワーク内を横移動
3. **ペイロード実行**: メインペイロード `servertool.exe` を手動でダウンロードして実行
4. **暗号化**: 最近更新されたファイルから優先的に暗号化
5. **連絡**: ランサムノートは生成せず、別経路で被害者に連絡

### 暗号化アルゴリズム

| 要素 | 詳細 |
|------|------|
| 暗号方式 | ChaCha20-Poly1305 |
| 鍵 | 32バイトマスターキー（ファイルごとにランダム IV） |
| 鍵導出 | Argon2id → SHA-256 → HKDF-SHA256 |
| 整合性検証 | SHA-256 ハッシュ |
| 処理単位 | 1 MB チャンク |
| ファイル優先順位 | 更新日時が新しいファイル順（同タイムスタンプはアルファベット順） |

### 身代金要求と被害状況

- Threatdown が確認した被害者は少なくとも5件
- Standard Bank への攻撃では 1 BTC の身代金を要求、拒否された
- 身代金要求書（テキストファイル）やデスクトップ壁紙変更は行わず、法的証拠の痕跡を最小化

### RaaS でない点が示す意味

多くのランサムウェアグループは RaaS モデルでアフィリエイトを募集するが、Prinz Eugen は現時点でアフィリエイト募集なし。被害件数が少なく標的型攻撃に近い運営形態とみられ、追跡が困難。

### 対策

- RDP の公開を最小化し、強力な認証（MFA）を適用
- RMM ツールの利用ログを監視し、不審な実行を即検知
- `servertool.exe` を含む不審バイナリのプロセス挙動監視
- 重要ファイルのオフラインバックアップを定期的に検証

---

## 関連記事

なし
