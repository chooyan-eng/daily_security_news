# Shai-Hulud サプライチェーン攻撃 - npm/PyPIで170+パッケージ汚染、SLSA Build Level 3も突破

- **日付**: 2026-06-19
- **出典**: [SecurityWeek](https://www.securityweek.com/over-100-npm-pypi-packages-hit-in-new-shai-hulud-supply-chain-attacks/)
- **トピック**: [Red Hat npmサプライチェーン攻撃（Miasma）](../topics/redhat-npm-supply-chain-miasma.md)
- **分類**: 関連

## 概要

TeamPCPグループによるShai-Hulud供給チェーン攻撃の新たな波（Mini Shai-Hulud）が確認された。2026年5月11〜12日に170以上のnpmパッケージと2つのPyPIパッケージが同時に汚染された。SLSA Build Level 3（ビルドプロセス完全性の最高レベル）を突破した業界初の攻撃として注目されており、セキュリティ証明書への信頼の限界を示した。

## 詳細

### Shai-Hulud全体のキャンペーン概要

Shai-HuludはTeamPCPが2025年9月から展開している一連のサプライチェーン攻撃キャンペーンの総称である。

| 指標 | 値 |
|------|-----|
| 攻撃開始 | 2025年9月 |
| 累積被害パッケージ | 170+（npm）、2（PyPI）|
| 悪意あるバージョン数 | 404件以上（Mini Shai-Hulud単独） |
| 累積週間ダウンロード | 約5億1800万 |
| 確認被害組織 | 大手銀行、Fortune 500、政府機関 |

### Mini Shai-Hulud（最新波）

2026年5月11日にMicrosoft Security Researchが特定した最新の波。

**特徴**:
- npmとPyPIの両エコシステムを同時攻撃（業界初の同時攻撃）
- SLSA Build Level 3認証付きパッケージも汚染に成功（業界初）
- 影響を受けた著名プロジェクト: TanStack、Mistral AI、UiPath、OpenSearch

### 技術的手法

**感染メカニズム**:
- `preinstall`（npm）/ `import`フック（PyPI）を悪用したインストール時自動実行
- Bunランタイムを使用したステージング
- 永続化デーモンによる侵害の維持

**窃取対象**:
- CI/CD認証情報（GitHub Actions、GitLab CI等）
- クラウド認証情報（AWS、GCP、Azure）
- 開発者認証情報（SSH鍵、npmトークン等）

**自己拡散メカニズム**:
- 窃取した認証情報を使用して、追加パッケージに汚染されたバージョンを公開
- これにより感染が連鎖的に拡大する「ワーム」的な動作を実現

### SLSA Build Level 3の突破

SLSA（Supply-chain Levels for Software Artifacts）はサプライチェーン攻撃に対する段階的な防御フレームワーク。Build Level 3はビルドプロセスの完全性を保証する最高レベルの証明であり、攻撃者がビルド時のプロセス制御を取得することでこの保証を覆した。これは「プロセス完全性の証明だけではサプライチェーン攻撃を防げない」ことを示す重大な発見である。

### Miasma（@redhat-cloud-services攻撃）との関連

2026年6月16日に詳細が明らかになったMiasma（@redhat-cloud-servicesネームスペースへの攻撃）との技術的関連性が明確化されている。同一のTeamPCPグループが複数の戦線でサプライチェーン攻撃を展開していることが確認された。

---

## 関連記事

- [Shai-Hulud自己拡散型マルウェア、npm/PyPIで320件以上のパッケージを汚染：Miasmaとの関連が明確化](../articles/2026-06-16-shai-hulud-supply-chain-worm-320-packages.md) - 直前の波に関する詳細分析
- [Red Hat npmパッケージを標的としたサプライチェーン攻撃「Miasma」、32件のパッケージが侵害](../articles/2026-06-16-redhat-npm-supply-chain-attack-miasma.md) - Miasmaキャンペーンの初報
