# Rust クレート arrayref サプライチェーン攻撃（2026年）

## 概要

crates.io上の人気Rustクレート arrayref、internment、append-only-vec が乗っ取られたメンテナーアカウントから悪意あるバージョンとして公開されたサプライチェーン攻撃。typosquatパッケージ `proc-macro1`（正規の`proc-macro2`を模倣）への依存を追加し、そのビルドスクリプト`build.rs`がコンパイル時にOS別ペイロードを展開する手口。北朝鮮関連キャンペーンとの重複が指摘されている。

**同一性の判断に役立つ情報：**
- 攻撃発生日: 2026年8月20日 01:17 UTC〜
- 悪意あるバージョン: arrayref@0.3.10、internment@0.8.7、append-only-vec@0.1.9
- 手口: typosquatパッケージ `proc-macro1`（`proc-macro2`模倣）への依存追加＋ビルド時実行（build.rs）
- 影響規模: arrayrefのみで生涯DL数245百万件超、internment+append-only-vecで約1,900万件
- 影響コンポーネント: egui、eframe、iced、blake3、Ethereum/Solana関連
- 削除までの時間: 86〜107分
- 攻撃者推定: 北朝鮮関連（UNC1069のaxios npm攻撃とのインフラ重複、Google Cloud Threat Intelligence分析）

## タイムライン

- [2026-08-20 Rust クレート arrayref/internment/append-only-vec がビルド時ドロッパーで汚染、245百万DL超に影響](../articles/2026-08-20-rust-arrayref-supply-chain-attack.md)
