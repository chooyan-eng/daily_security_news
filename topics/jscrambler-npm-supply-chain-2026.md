# jscrambler npm サプライチェーン攻撃 - Rust製インフォスティーラー混入（2026年7月）

## 概要

JavaScript難読化ツールを提供するセキュリティベンダー Jscrambler の npm パッケージ「jscrambler」および関連プラグインが、2026年7月11日に侵害され、悪意あるバージョンが正規のメンテナーアカウントから npm レジストリに公開された。インストール時に Rust 製のクロスプラットフォーム型インフォスティーラーが実行され、クラウド認証情報や暗号資産ウォレット、パスワードマネージャーのデータなどを窃取する。

**同一性の判断に役立つ情報：**
- 対象パッケージ: jscrambler（およびjscrambler-webpack-plugin、gulp-jscrambler、grunt-jscrambler、jscrambler-metro-plugin等の関連パッケージ）
- 悪性バージョン: 8.14.0、8.16.0、8.17.0、8.18.0、8.20.0（約3時間の間に連続公開）
- 発覚・公開日: 2026年7月11日
- 侵害経路: 正規メンテナーアカウント経由（npmアカウントまたはビルドパイプラインの侵害と推測）
- ペイロード: Rust製インフォスティーラー（Windows/macOS/Linux対応、AWS/Azure/GCPの認証情報、MetaMask/Phantom/Exodus等の暗号資産ウォレット、Bitwardenボルト等を標的）
- ダウンロード数: 悪性版合計1,479件（削除前）
- 対応: 該当バージョンは全て非推奨化・npm依存解決から除外済み、安全な版として8.22.0等が提供

## タイムライン

- [2026-07-14 jscrambler npmパッケージが侵害され、開発者端末を狙うRust製インフォスティーラーが混入](../articles/2026-07-14-jscrambler-npm-supply-chain.md)
