# npmパッケージ「jscrambler」が侵害、Rust製情報窃取マルウェア「IronWorm」をインストール時に展開

- **日付**: 2026-07-13
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/compromised-jscrambler-8140-npm-release.html), [TechNadu](https://www.technadu.com/supply-chain-attack-jscrambler-npm-package-compromised-targeting-wallets-ai-tools-cloud-credentials/630836/)
- **分類**: 関連

## 概要

JavaScript難読化ツールを提供するセキュリティベンダーJscramblerのnpmパッケージが、侵害されたnpm発行用クレデンシャルを通じて汚染された。バージョン8.14.0など5つのバージョンにクロスプラットフォーム（Windows/macOS/Linux）対応のRust製情報窃取マルウェア「IronWorm」が仕込まれ、クラウド認証情報や暗号資産ウォレット、パスワードマネージャーのデータを窃取していた。JFrogはIronWormを、以前から追跡しているShai-Hulud系統のマルウェアと関連付けている。

## 詳細

### 侵害の経緯

Jscrambler社は、攻撃者が侵害されたnpm発行用クレデンシャルを用いてパッケージを公開したことを確認した。悪意あるバージョンは約3時間の間に立て続けに公開されており、8.14.0・8.16.0・8.17.0・8.18.0・8.20.0の5バージョンが対象。8.14.0・8.16.0・8.17.0では`preinstall`フックからマルウェアが起動する一方、8.18.0・8.20.0ではドロッパーがパッケージ本体のコードやCLIに組み込まれ、`npm install --ignore-scripts`でも実行を防げない設計になっていた点が特に危険とされる。

### IronWormペイロードの機能

IronWormはRustで書かれたクロスプラットフォーム対応の情報窃取マルウェアで、開発者マシン上の以下の情報を収集しTLS経由でドロップサーバーへ送信する。

- AWS・Azure・Google Cloudのクラウド認証情報（CIランナーが使用するメタデータエンドポイントを含む）
- MetaMask・Phantom・Exodus等の暗号資産ウォレットとシードフレーズ
- Bitwardenパスワードマネージャーのボルト

さらに、環境変数や`.npmrc`ファイル内のnpmトークンを探索し、レジストリに対して有効性を確認した上でダウンロード数の多いパッケージを選定、悪意ある`setup.mjs`のpreinstallスクリプトを注入して`registry.npmjs.org`へ生のHTTP PUTリクエストで再公開するという自己拡散的な挙動も確認されている。

### 発見と帰属

JFrogは1か月前に文書化していたIronWormと同一のペイロードであることを特定し、Shai-Hulud系統のマルウェアとの関連を指摘している。Socketは5つの悪意あるjscramblerバージョンすべてが同一の攻撃者によるものであるとしている。

### 対策

- jscramblerを利用しているプロジェクトは、8.14.0・8.16.0・8.17.0・8.18.0・8.20.0がインストールされていないか確認し、安全なバージョンへの更新・再インストールを行うこと
- クラウド認証情報、npmトークン、暗号資産ウォレットのローテーションを検討すること
- `--ignore-scripts`だけでは防げないケースがあるため、CI/CDパイプラインでの依存関係の完全性検証（lockfile検証、SBOM監視等）を強化すること

---

## 関連記事

- [Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化](../articles/2026-06-16-shai-hulud-supply-chain-worm-320-packages.md) - JFrogがIronWormペイロードをShai-Hulud系統のマルウェアと関連付けており、npmエコシステムを狙う自己拡散型サプライチェーン攻撃の系譜が継続している可能性がある。
