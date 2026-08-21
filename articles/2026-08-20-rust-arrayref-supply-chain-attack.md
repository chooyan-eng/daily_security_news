# Rust クレート arrayref/internment/append-only-vec がビルド時ドロッパーで汚染、245百万DL超に影響

- **日付**: 2026-08-20
- **出典**: [The Hacker News](https://thehackernews.com/2026/08/rust-supply-chain-attack-puts-build.html) / [Rust Blog](https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/) / [BleepingComputer](https://www.bleepingcomputer.com/news/security/hackers-poison-arrayref-rust-crate-to-push-infostealer-malware/) / [Wiz Blog](https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns)
- **トピック**: [Rust クレート arrayref サプライチェーン攻撃（2026年）](../topics/rust-arrayref-supply-chain-attack-2026.md)
- **分類**: 新規

## 概要

crates.io上の人気Rustクレート arrayref@0.3.10、internment@0.8.7、append-only-vec@0.1.9 が乗っ取られたメンテナーアカウントから悪意あるバージョンとして公開された。typosquatパッケージ proc-macro1 への依存を追加し、`build.rs` がコンパイル時にOS別ペイロードを展開する仕組み。arrayrefだけで生涯ダウンロード数245百万件超、blake3やEthereum/Solana関連コンポーネントにも影響が及ぶ規模だった。北朝鮮関連キャンペーンとの重複が指摘されている。

## 詳細

### 攻撃の発端

2026年8月20日01:17 UTC、著名なRust開発者David Tolnayを騙るGitHubアカウントが作成され、続いてcrates.ioレジストリにも同様のなりすましアカウントが作られた。このアカウントを使い、既存の正規メンテナーが管理していたarrayref、internment、append-only-vecの3クレートに悪意あるバージョンが公開された。

### 攻撃手法：typosquatとビルド時実行

攻撃者は各クレートの依存関係に `proc-macro1` という新規パッケージを追加した。これは広く使われる正規パッケージ `proc-macro2` に酷似した名称のtyposquatパッケージである。クレート本体のソースコードは改変せず、この不正な依存だけを差し込む手口により、コードレビューでの検知を困難にしている。

`proc-macro1` には `build.rs` というビルドスクリプトが含まれており、`cargo build` の実行時に自動的に実行される。このスクリプトは、base64エンコードされた断片からインフラストラクチャを再構築し、ホストOS（Linux x86-64、Windows x86-64、macOS x86-64、macOS ARM64）に応じたペイロードを選択して展開する。ユーザーがビルドを実行するだけで、明示的な実行操作なしにマルウェアが起動する点が特徴である。

### 影響範囲

arrayrefは生涯ダウンロード数が245百万件を超える広く使われるクレートで、Rust製GUIフレームワークのegui、eframe、iced、暗号ハッシュ関数実装のblake3のほか、Ethereum・Solana関連のコンポーネントでも利用されている。internmentとappend-only-vecを合わせたダウンロード数も約1,900万件に達する。

### 検知と対応の速さ

3つの悪意あるリリースは公開から86分から107分以内にすべて削除された。crates.ioチームとRustセキュリティチームが迅速に対応したことで、大規模な感染拡大は回避されたとみられる。Rust公式ブログも同日中にインシデントの詳細を公表した。

### 攻撃者の推定

Google Cloud Threat Intelligenceの分析によれば、今回使用されたインフラの一部は、Mandiantが北朝鮮（UNC1069）に帰属させたaxios npmパッケージへの攻撃で観測されたものと重複している。このため、北朝鮮系脅威アクターとの関連が疑われている。

### 開発者への示唆

- `Cargo.lock` の差分監査を継続的に行い、見慣れない依存パッケージの追加を検知する
- ビルドスクリプト（`build.rs`）を含む新規依存パッケージについては、追加時に特に注意深くレビューする
- typosquat対策として、依存パッケージ名のタイプミスやよく似た名称のパッケージ追加をCIで検出する仕組みを導入する
- 影響を受けた3クレートを利用しているプロジェクトは、該当バージョンの利用有無を確認し、該当する場合はクレデンシャルのローテーションを行う
