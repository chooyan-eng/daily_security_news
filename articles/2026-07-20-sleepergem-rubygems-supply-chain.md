# SleeperGem：休眠アカウント乗っ取りによるRubyGemsサプライチェーン攻撃、モバイルアプリ開発者も標的に

- **日付**: 2026-07-20
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/sleepergem-uses-three-malicious.html)
- **トピック**: [SleeperGem RubyGemsサプライチェーン攻撃（2026年7月）](../topics/sleepergem-rubygems-supply-chain-2026.md)
- **分類**: 新規

## 概要

Rubyエコシステムを標的とした新たなサプライチェーン攻撃「SleeperGem」が確認された。攻撃者は休眠状態にあった正規のRubyGemsメンテナーアカウントを乗っ取り、3つの悪意あるgemパッケージを公開。CI/CD環境を回避し開発者のローカルマシンを狙って永続的なネイティブマルウェアをインストールする点が特徴で、モバイルアプリのCI/CDツール「fastlane」向けプラグインを装ったパッケージも含まれていた。

## 詳細

### 攻撃手口の特徴

「SleeperGem」という名称は、あらかじめ攻撃用に用意された不正アカウントではなく、単に長期間活動を休止していた実在の正規アカウントが乗っ取り対象として選ばれたことに由来する。休眠アカウントは違和感なく乗っ取れるため、コミュニティの警戒網をすり抜けやすい。

### 悪意あるパッケージ

以下の3つの悪意あるRubyGemsパッケージが確認された：

1. **git_credential_manager** — MicrosoftのGit Credential Managerを模倣した名称のパッケージ
2. **Dendreo**
3. **fastlane-plugin-run_tests_firebase_testlab** — iOS/Androidアプリのビルド・デプロイ自動化で広く使われるCI/CDツール「fastlane」向けのプラグインを装ったパッケージ

### 検知回避のメカニズム

インストールされたマルウェアは、感染システム上で約30種類の環境変数をスキャンする。GitHub Actions、GitLab CI、CircleCI、Travis CI、Jenkins、Vercelなどに関連する環境変数が検出された場合、マルウェアは直ちに処理を終了する。これは、使い捨てのCIランナー上での実行を意図的に回避し、開発者の実マシン上でのみ動作させ、永続化を狙った設計であるとみられる。

### モバイルアプリ開発への影響

3つの悪意あるパッケージのうち「fastlane-plugin-run_tests_firebase_testlab」は、iOS/Androidアプリ開発で広く使われるビルド自動化ツールfastlaneのプラグインを騙るものであり、モバイルアプリ開発者のマシンが直接の標的となっていた点は注目に値する。モバイルアプリのビルド・署名鍵やFirebase関連の認証情報が開発者マシン上に保存されているケースは多く、侵害された場合のサプライチェーンリスクは大きい。

### 対応推奨

- 上記3パッケージ（git_credential_manager、Dendreo、fastlane-plugin-run_tests_firebase_testlab）がインストールされていないか、Gemfile・Gemfile.lockを確認
- モバイルアプリ開発チームは、fastlane関連プラグインの出所・メンテナー状況を再確認
- 開発者ローカルマシンにおいてもCI環境と同水準のマルウェアスキャン・依存関係監査を実施することを推奨
- RubyGemsメンテナーアカウントについても、休眠アカウントの乗っ取りリスクを踏まえ、多要素認証の徹底とアカウント活動の定期監査を推奨
