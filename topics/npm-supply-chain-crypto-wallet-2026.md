# npmサプライチェーン攻撃・暗号資産ウォレット窃取（2026年7月）

## 概要

DeFiブロックチェーン基盤Injectiveの公式SDK「@injectivelabs/sdk-ts」のGitHubリポジトリが侵害され、npm経由で暗号資産ウォレットの秘密鍵・シードフレーズを窃取する悪意あるバージョン1.20.21が配布された事案。2026年7月8日公開。関連する17個のスコープ付きパッケージにも影響が波及。同時期にjscrambler等、他のnpmパッケージでも類似のサプライチェーン侵害が相次いでいる。

**同一性の判断に役立つ情報：**
- 侵害パッケージ: @injectivelabs/sdk-ts（および関連17パッケージ）
- 悪意あるバージョン: 1.20.21
- 公開日: 2026年7月8日
- マルウェア機能: ウォレット秘密鍵・ニーモニックシードフレーズの窃取、Base64エンコードしInjective公式風エンドポイントへ送信
- 検知企業: Socket、Ox Security、StepSecurity

## タイムライン

- [2026-07-12 Injective Labs の GitHub リポジトリが侵害、npm 経由で暗号資産ウォレット窃取パッケージが配布](../articles/2026-07-12-injective-labs-sdk-npm-wallet-stealer.md)
