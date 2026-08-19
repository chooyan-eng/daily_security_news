# Shai-Hulud ワーム：6月の新波で 100件超の npm・PyPI パッケージが再度侵害

- **日付**: 2026-06-26
- **出典**: [SecurityWeek](https://www.securityweek.com/over-100-npm-pypi-packages-hit-in-new-shai-hulud-supply-chain-attacks/)
- **トピック**: [TeamPCPサプライチェーン攻撃（Trivy/Bitwarden/Checkmarx）（2026年）](../topics/teampcp-supply-chain-2026.md)
- **分類**: 続報

## 概要

TeamPCP が運用する自己増殖型ワーム「Shai-Hulud」の新たな攻撃波が 2026年6月1日以降に確認され、100件超の npm・PyPI パッケージが侵害された。2025年9月から始まったキャンペーンの最新フェーズで、SLSA プロベナンス署名偽造・GitHub OIDC トークン窃取・AI コーディングツールへの感染拡大という高度な手法が引き続き使用されている。

## 詳細

**6月新波の概要**

2026年6月1日以降、Shai-Hulud の新たな反復（イテレーション）が npm と PyPI エコシステムにわたる大規模な協調攻撃として確認された。6月の波では100件超のパッケージが侵害されており、これは 2025年9月の開始以来の累計 170件超のパッケージ侵害に加わる形となる。

**CVE-2026-45321 の悪用（TanStack）**

6月の波の中で注目される攻撃は、TanStack の GitHub Actions CI/CD 設定の脆弱性を突いた CVE-2026-45321 の悪用：

1. 攻撃者が `TanStack/router` の fork をリネームして偽装アカウントを作成
2. `pull_request_target` ワークフローをトリガーするプルリクエストを開く
3. ベースリポジトリの信頼済みコンテキストで攻撃者コードが実行される
4. GitHub Actions キャッシュに悪意あるバイナリを注入
5. ランナーのプロセスメモリから OIDC トークンを直接抽出
6. npm のフェデレーションエンドポイントでトークンを完全な公開資格情報に交換
7. **6分以内に 42パッケージにわたる 84件の悪意あるバージョンが公開**、全て Sigstore による有効な SLSA Build Level 3 プロベナンス証明を持つ

**Miasma バリアント（Red Hat npm 名前空間）**

2026年6月1日、`@redhat-cloud-services` npm 名前空間下で公開された 32件以上のパッケージが侵害。6月5日までに 57件超の npm パッケージ・300件超の悪意あるバージョンが確認された。Miasma ペイロードは Claude Code・GitHub Copilot・Gemini CLI を含む 13種の AI コーディングツールの SessionStart フック に自己注入する自己拡散ワームとして動作する。

**Hades バリアント（PyPI・バイオインフォマティクス）**

2026年6月8日、人気グラフ機械学習パッケージ `ensmallen` の v0.8.101 が高度なサプライチェーン侵害を含むことが発覚。計算生物学・バイオインフォマティクス・遺伝子型・表現型解析関連の約24件のパッケージに同一のペイロードが確認された。

**TeamPCP との帰属**

Unit42（Palo Alto Networks）は、2025年9月から継続する一連の攻撃を TeamPCP（別名 UNC6780）に帰属している。SLSA プロベナンス偽造・OIDC トークン窃取・GitHub の C2 チャンネルとしての悪用が TeamPCP の特徴的 TTP である。
