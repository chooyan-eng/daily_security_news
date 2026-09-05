# Packagist悪意あるComposerテーマパッケージ・iOSスパイウェア配信事案（2026年）

## 概要

PHPパッケージリポジトリPackagistに公開された13件の悪意あるComposerテーマパッケージ（vsmov・vsphim・haiau009・chilltvcms・ophimcms系名前空間）が、ベトナム語圏の動画・漫画配信サイトにJavaScriptを注入し、未パッチのiPhoneに対してWebKitからカーネルに至るエクスプロイトチェーンでスパイウェアを配信していた事案。2026年8月12日頃に再展開されたペイロードは、iOSキーチェーンから暗号資産ウォレット（Bitget、BitKeep、Bitpie、Phantom、Tonkeeper、Trust Wallet、OKX等）の復元シードを窃取する機能を備える。

**同一性の判断に役立つ情報：**
- 配布経路: Packagist上のComposerテーマパッケージ13件（vsmov/theme-dy、vsmov/theme-rrdyw、vsphim/theme-heovl、haiau009/kkphim-legend、chilltvcms/theme-legend 等）
- 標的サイト: ベトナム語圏の動画・漫画ストリーミングサイト
- 攻撃対象: iOS 18.4〜18.6.x系（WebKit-to-kernelエクスプロイトチェーン）
- 追加ペイロード: iOSキーチェーン暗号資産ウォレットシード・ニーモニック窃取機能（2026年8月12日頃再展開）
- 対象ウォレット: Bitget、BitKeep、Bitpie、Phantom、Tonkeeper、Trust Wallet、OKX
- 推定攻撃者: コミットメタデータからベトナム拠点のグループと推定
- 対策バージョン: iOS 18.7.3以降 または iOS 26.2以降

## タイムライン

- [2026-09-05 Packagistの悪意あるテーマパッケージ13件、未パッチiPhoneから暗号資産ウォレットのシード情報を窃取](../articles/2026-09-05-packagist-malicious-packages-ios-spyware.md)
