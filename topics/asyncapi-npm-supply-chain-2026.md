# @asyncapi npmサプライチェーン攻撃（2026年7月）

## 概要

npmの@asyncapi organizationが2026年7月14日、協調的なサプライチェーン攻撃で侵害された。4パッケージ・5バージョンが悪意あるローダーを注入された状態で再公開され、モジュールロード（import/require）時にペイロードが実行される新手口が使われた。@asyncapi/specsが多数のツーリングの推移的依存関係であるため、開発者端末・CI/CD・本番サービスまで影響が波及。週間約200万ダウンロード規模のパッケージ群が対象。Microsoft Threat Intelligenceが発見・報告。

**同一性の判断に役立つ情報：**
- 対象: npm @asyncapi organization（4パッケージ・5バージョン）
- 侵害日: 2026年7月14日
- 手口: モジュールロード（import/require）時のペイロード実行（従来のpostinstallフック型と異なる）
- 発見: Microsoft Threat Intelligence
- 影響規模: 週間約200万ダウンロード

## タイムライン

- [2026-07-17 npmパッケージ「@asyncapi」がサプライチェーン攻撃で侵害 ― import時に悪意あるローダーを実行、週200万DLに影響](../articles/2026-07-17-asyncapi-npm-supply-chain-attack.md)
