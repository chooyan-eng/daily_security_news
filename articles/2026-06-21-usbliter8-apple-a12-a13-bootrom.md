# usbliter8 — Apple A12/A13 チップのパッチ不可能な BootROM エクスプロイト公開

- **日付**: 2026-06-21
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/unpatchable-usbliter8-exploit-breaks.html) / [9to5Mac](https://9to5mac.com/2026/06/18/new-unpatchable-exploit-targets-apple-devices-with-a12-and-a13-chips/) / [Privacy Guides](https://www.privacyguides.org/news/2026/06/19/unpatchable-exploit-found-apples-a12-and-a13-chips/)
- **トピック**: [usbliter8 — Apple A12/A13 パッチ不可能 BootROM エクスプロイト（2026年）](../topics/usbliter8-apple-bootrom-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業 Paradigm Shift が2026年6月18日、Apple の A12/A13/S4/S5 チップを搭載するデバイスを対象としたパッチ不可能な BootROM エクスプロイト「usbliter8」の技術詳細と動作する PoC を公開した。USB コントローラーのハードウェアバグとファームウェア設定不備を組み合わせた手法で、checkm8 と同様に物理アクセスと DFU モードが必要。iOS アップデートでは修正不可能であり、影響を受けるデバイスユーザーには新機種への移行が推奨される。

## 詳細

### 影響を受ける SoC・デバイス

| SoC | 代表デバイス |
|-----|------------|
| A12 | iPhone XS、iPhone XS Max、iPhone XR |
| A13 | iPhone 11、iPhone 11 Pro/Max |
| S4 | Apple Watch Series 4 |
| S5 | Apple Watch Series 5 |

iPhone 12 以降（A14〜）および Apple Watch Series 6 以降は影響なし。

### 脆弱性の仕組み

usbliter8 は2段階の脆弱性を組み合わせる：

1. **USB コントローラーのハードウェアバグ**: USB DMA（Direct Memory Access）バッファのアンダーフロー脆弱性。USB コントローラーがメモリ境界チェックを正しく行わない設計欠陥であり、ファームウェアで修正不能。
2. **SecureROM ファームウェアの設定不備**: ハードウェアバグとの組み合わせにより SecureROM（ブートチェーン の最上位ロジック）のコード実行フローを奪取可能。

**A13 での追加ハードル**: A13 の SecureROM は PAC（Pointer Authentication Codes）を実装しており、単純な RIP リダイレクトが不可能。Paradigm Shift は複数段階のメモリ破壊によって USB 割り込みハンドラを制御し PAC を迂回する手法を発見した。

### checkm8 との比較

| 項目 | checkm8 | usbliter8 |
|------|---------|----------|
| 物理アクセス必要 | ✓ | ✓ |
| DFU モード必要 | ✓ | ✓ |
| パッチ不可能 | ✓ | ✓ |
| 対象チップ世代 | A5〜A11 | A12〜A13、S4/S5 |
| PAC バイパス | 不要 | 必要（A13） |

### セキュリティへの影響

- **ジェイルブレイク**: iOS セキュリティモデルを完全に迂回可能
- **フォレンジック取得**: 法執行機関や攻撃者がデバイスの全データを抽出可能
- **マルウェア永続化**: ブートプロセス段階でのコード実行により検知困難な永続マルウェアを設置可能
- **企業 MDM バイパス**: MDM プロファイルや企業セキュリティポリシーを無効化可能

### 緩和策と推奨対応

ファームウェアパッチによる修正は構造的に不可能。Paradigm Shift は以下を推奨：

- 影響を受けるデバイスの廃棄を検討（iPhone 11 以前、Apple Watch Series 5 以前）
- 企業環境では当該機種を使用禁止または厳重管理
- 高機密情報を扱う利用者は A14 以降（iPhone 12 以降）への移行

---

## 関連記事

なし
