# SleeperGem RubyGemsサプライチェーン攻撃（2026年7月）

## 概要

休眠状態のRubyGemsメンテナーアカウントを乗っ取り、3つの悪意あるgemパッケージ（git_credential_manager、Dendreo、fastlane-plugin-run_tests_firebase_testlab）を公開したサプライチェーン攻撃「SleeperGem」。CI環境（GitHub Actions、GitLab CI、CircleCI等）を検知し実行を回避することで、開発者のローカルマシンのみを狙って永続的なネイティブマルウェアをインストールする。モバイルアプリ向けCI/CDツールfastlaneのプラグインを装ったパッケージも含まれる。

**同一性の判断に役立つ情報：**
- 通称: SleeperGem
- 攻撃手法: 休眠メンテナーアカウントの乗っ取り
- 悪意あるパッケージ: git_credential_manager、Dendreo、fastlane-plugin-run_tests_firebase_testlab
- 検知回避: 約30種類のCI関連環境変数をチェックし、検出時は処理終了（開発者ローカルマシンのみ標的）
- 公開日: 2026年7月20日報道

## タイムライン

- [2026-07-20 SleeperGem：休眠アカウント乗っ取りによるRubyGemsサプライチェーン攻撃、モバイルアプリ開発者も標的に](../articles/2026-07-20-sleepergem-rubygems-supply-chain.md)
