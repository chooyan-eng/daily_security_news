# Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化

- **日付**: 2026-06-16
- **出典**: [SecurityWeek](https://www.securityweek.com/over-320-npm-packages-hit-by-fresh-mini-shai-hulud-supply-chain-attack/), [StepSecurity](https://www.stepsecurity.io/blog/mini-shai-hulud-is-back-a-self-spreading-supply-chain-attack-hits-the-npm-ecosystem), [OX Security](https://www.ox.security/blog/shai-hulud-here-we-go-again-170-packages-hit-across-npm-pypi/)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 続報

## 概要

2025年9月から続くnpm・PyPI向け自己拡散型マルウェアキャンペーン「Shai-Hulud」の最新動向が明らかになった。2026年6月時点で320件以上のnpmパッケージが汚染されており、累計週間ダウンロード数は5億1800万件を超える。最新亜種「Miasma」および「Hades」は当初Red Hatのnpmネームスペースを標的にしていたが、TanStack、Mistral AI、Guardrails AIなど著名なAI・フロントエンドライブラリの開発者認証情報を悪用した侵害に拡大している。

## 詳細

### Shai-Hulud キャンペーンの全体像

脅威グループ「TeamPCP」が主導するShai-Hulud（ドゥーン小説に登場する巨大砂虫に由来）は、自己拡散型（ワーム型）のサプライチェーン攻撃キャンペーンである。

**キャンペーンのタイムライン**:
- **2025年9月〜2026年2月**: 初期Shai-Hulud活動（TanStack、UiPath等への侵害）
- **2026年5月**: Mini Shai-Hulud亜種がTanStack npmパッケージ等を侵害
- **2026年6月1日〜**: 最新亜種「Miasma」「Hades」が活性化
- **2026年6月5日**: Wiz Researchが`@redhat-cloud-services`ネームスペースの32件以上のパッケージ侵害を確認（当時）

### 自己拡散メカニズム

Shai-Hulud系マルウェアの特徴的な動作：

1. **初期侵害**: フィッシングや漏洩した開発者認証情報を通じてnpmアカウントを乗っ取る
2. **マルウェア注入**: パッケージの`preinstall`スクリプト、`binding.gyp`、またはメインJSファイルに悪意あるコードを追加
3. **自己拡散**: インストール時に実行されるコードが被害者の開発環境から別のnpmトークンを窃取し、被害者が管理する他のパッケージへも感染を拡大
4. **持続性**: CI/CDパイプラインのクレデンシャルを使ってクラウド環境への継続的アクセスを確保

### SLSA Build Level 3 の突破

本キャンペーンはソフトウェアサプライチェーンセキュリティの重要なマイルストーンを破った：有効な**SLSA Build Level 3**プロベナンス署名を持つパッケージの侵害に成功したことが確認された。SLSA（Supply-chain Levels for Software Artifacts）はサプライチェーンの完全性を担保するフレームワークだが、ビルドプロセス自体ではなく、パッケージ公開に使用するnpmトークンを窃取することでプロセス完全性の保証を無効化した。

### 主な侵害パッケージ（累積）

| パッケージ | エコシステム | 週間DL数（概算） |
|---|---|---|
| TanStack Query / Router | npm | 数百万 |
| Mistral AI SDK | npm/PyPI | 数十万 |
| Guardrails AI | PyPI | 数万 |
| @redhat-cloud-services/* (32件+) | npm | 約8万（合計） |
| UiPath Python SDK | PyPI | 数万 |

### Miasma亜種（2026年6月）の特徴

Red Hatを主な標的としたMiasma亜種の特徴：
- `@redhat-cloud-services`ネームスペースの正規パッケージを悪意あるバージョンに置き換え
- `binding.gyp`（ネイティブモジュールビルド設定）を悪用したインストール時実行
- CI/CDクレデンシャル（AWS、GCP、GitHub Actions等）の窃取を目的
- 2026年6月1日時点でWiz Researchが検出・npmに報告

### 影響評価と現在の状況

- 今日（2026年6月16日）時点で累計320件超のnpmパッケージへの侵害を確認
- npmおよびPyPIは報告を受けたパッケージの削除を進めているが、ワーム的な自己拡散により追いかけっこの状態が継続
- CISA、GitHub、Googleが共同でサプライチェーンセキュリティのアドバイザリを発表予定

### 推奨アクション

- **npm audit**: 依存パッケージの整合性確認（`npm audit signatures`）
- **プロベナンス確認**: npmプロベナンス検証を活用しても不十分な場合があることに注意
- **CI/CDシークレット**: GitHub Actions、AWS IAMロール等のアクセスキーを即時ローテーション
- **SBOM活用**: Software Bill of Materialsを活用した依存関係の可視化

---

## 関連記事

- [Red Hat npmパッケージを標的としたサプライチェーン攻撃「Miasma」、32件のパッケージが侵害](../articles/2026-06-16-redhat-npm-supply-chain-attack-miasma.md) - Miasma亜種の初報
