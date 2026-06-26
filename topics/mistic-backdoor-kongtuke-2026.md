# Mistic バックドア・KongTuke ランサムウェア IAB（2026年）

## 概要

2026年6月に Symantec・Zscaler ThreatLabz が詳細を報告した新型ファイルレスバックドア「Mistic」（別名：MLTBackdoor）と、ランサムウェア初期アクセスブローカー（IAB）「KongTuke」（別名：404 TDS・Chaya_002・LandUpdate808・TAG-124・Woodgnat）の連携。Mistic は保険・教育・IT・専門サービス分野を標的に、ペイロードをメモリ上でのみ実行するファイルレス設計と自己削除機能を持ち、DLL サイドローディングで展開される。KongTuke は Qilin・Interlock・Rhysida・Akira・8Base・Black Basta に企業ネットワークアクセスを供給している。

**同一性の判断に役立つ情報：**
- バックドア名: Mistic（別名：MLTBackdoor）
- IAB 名: KongTuke（別名：404 TDS・Chaya_002・LandUpdate808・TAG-124・Woodgnat）
- 関連 RAT: ModeloRAT（Python製）
- 活動開始: 2026年4月頃〜
- 標的分野: 保険・教育・IT・専門サービス
- 関連ランサムウェア: Qilin・Interlock・Rhysida・Akira・8Base・Black Basta
- 展開手法: DLL サイドローディング（正規 Microsoft 実行ファイルを悪用）
- 特徴: ファイルレス実行・自己削除キルスイッチ・コード難読化（約95%がジャンクコード）

## タイムライン

- [2026-06-25 新型ファイルレスバックドア「Mistic」と ランサムウェア IAB「KongTuke」の連携が明らかに](../articles/2026-06-25-mistic-backdoor-kongtuke-rab.md)
