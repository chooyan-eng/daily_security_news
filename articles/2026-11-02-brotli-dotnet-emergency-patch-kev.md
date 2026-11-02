# Brotli脆弱性(CVE-2026-111497)の悪用が確認、CISAがKEV追加・Microsoftが.NET緊急パッチ

- **日付**: 2026-11-02
- **出典**: [BleepingComputer](https://bleepingcomputer.com/news/security/cisa-warns-of-hackers-now-exploiting-critical-node2shell-flaw)
- **トピック**: [Brotli CVE-2026-111497「Node2Shell」境界外書き込みRCE（2026年10月）](../topics/brotli-cve-2026-111497-node2shell.md)
- **分類**: 続報

## 概要

Brotliデコーダの境界外書き込みCVE-2026-111497について、CISAが悪用を確認しKEVに追加。Microsoftは.NET向けの緊急パッチを公開し、シンガポールCSAも即時パッチ適用を呼びかけた。

## 詳細

- 悪用: CISAが10/28に悪用開始を警告。ELLIOが悪用トラフィックを観測し、公開エクスプロイトで実際にシェルが取れると確認(Help Net Security)。
- Node.js: 10/21に開示。修正版は26.12.1、24.22.1、22.23.4。EOLの20.x/23.x/25.xは影響を受けるが修正されない。
- .NET: Microsoftが緊急更新を公開。Brotli伸張は標準では無効で、有効化しているアプリが影響を受ける。
- 波及: curl、Pythonバインディング、Envoyなど、Brotliを同梱・利用するソフトにも影響し、システムライブラリの更新だけでは同梱コピーが残る。
- 期限: 連邦機関の対応期限は報道間で食い違う(11/10とする報道、10/29とする報道)。
- 出典: [BleepingComputer(.NET緊急パッチ)](https://www.bleepingcomputer.com/news/microsoft/microsoft-releases-emergency-net-patches-for-critical-brotli-flaw/amp/)、[Help Net Security](https://www.helpnetsecurity.com/?p=389353)。
- 注意: 検索結果の要約に基づく。

---
