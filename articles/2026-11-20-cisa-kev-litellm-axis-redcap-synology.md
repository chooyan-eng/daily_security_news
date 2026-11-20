# CISA、LiteLLM（CVE-2026-40217）・Apache Axis・REDCap・Synology DSMの4件をKEVに追加——ランサムウェア/クリプトマイニング/LLMjackingで悪用

- **日付**: 2026-11-20
- **出典**: [The Hacker News](https://thehackernews.com/2026/11/cisa-warns-of-4-exploited-flaws-linked.html)
- **トピック**: [LiteLLM AIゲートウェイ脆弱性チェーン](../topics/litellm-ai-gateway-vulnerabilities.md)
- **分類**: 続報

## 概要

米CISAは11月18日、実悪用が確認された4件の脆弱性をKEVカタログに追加した。AIゲートウェイLiteLLMのサンドボックスエスケープCVE-2026-40217、Apache Axis 1.xのCVE-2026-90436（CVSS 9.8）、研究データ収集WebアプリREDCapの未認証コードインジェクションCVE-2026-90817（CVSS 9.8）、Synology DSMの脆弱性が対象。ランサムウェア、クリプトマイニング、LLMjackingに関連付けられており、3件は対応期限が11月21日と極めて短い。

## 詳細

### 追加された4件（2026-11-18）

| CVE | 製品 | 概要 | 連邦機関の期限 |
|-----|------|------|---------------|
| CVE-2026-40217 | BerriAI LiteLLM | Python `exec()` サンドボックスエスケープによるコード実行。CVSSはv3で8.8、v4で5.9とする情報があり評価が割れている。1.83.11以降で修正との報道 | 2026-12-02 |
| CVE-2026-90436 | Apache Axis 1.x | CVSS 9.8。開発終了済みのJava製SOAPライブラリ。バグ種別は安全でないリフレクションとする情報とXXEとする情報がある。Apacheは1.xの修正リリースを予定せず、他のSOAPエンジンへの移行か、公開パッチを独自ビルドに適用することを推奨 | 2026-11-21 |
| CVE-2026-90817 | Vanderbilt REDCap | CVSS 9.8。未認証の攻撃者がサーバー上でコードを実行できるコードインジェクション。16.0.49、17.3.10、17.4.4以降は影響なし | 2026-11-21 |
| CVE-2024-10441（報道による。要確認） | Synology DiskStation Manager | コード実行 | 2026-11-21 |

- Synology、Apache Axis、REDCapの3件については、CISAがBOD 26-04に基づくフォレンジックトリアージも指示したと報じられている。
- LiteLLM、Apache Axis、REDCapには公開PoCが存在する（SecurityOnline）。
- KEV掲載は各脆弱性の悪用を示すもので、同一の攻撃者が4件すべてを使っていることを意味しない。

### LiteLLM CVE-2026-40217について

- 本リポジトリで追跡しているLiteLLM脆弱性チェーンの1件（従来CVSS 9.8と報じられていた `exec()` サンドボックスエスケープ）。LiteLLMのCVEとしては CVE-2026-42271（6月）、CVE-2026-35029／CVE-2026-59822（9月）に続くKEV入りとなる。
- 悪用目的として**LLMjacking**（窃取したAPIキーや侵害したゲートウェイを使い、被害者の課金でLLMを不正利用・転売する行為）が挙げられている。LiteLLMはOpenAI/Anthropic等100以上のプロバイダーのAPIキーを集約するため、侵害時は全プロバイダーのキーのローテーションが必要。
- 対応: 修正版への更新、管理API/プロキシの非公開化、マスターキー・仮想キー・プロバイダーキーのローテーション、利用量の異常監視。10月には1.107.0のサプライチェーン汚染もあったため、導入バージョンの出所確認も併せて行う。

### その他の技術的な補足

- **Apache Axis 1.x**は2006年頃に開発が止まったライブラリだが、業務系Webサービス（SOAP API）や製品組み込みで今も残存している。依存関係スキャンで `axis:axis` / `org.apache.axis:axis` の有無を確認し、Axis2/CXF等への移行を検討する。
- **REDCap**は医療・学術機関で広く使われるPHP製の研究データ収集Webアプリ。未認証RCEであり、インターネット公開インスタンスは即時更新と侵害調査が必要。

### 参考

- [CISA: Adds Four Known Exploited Vulnerabilities to Catalog](https://www.cisa.gov/news-events/alerts/2026/11/18/cisa-adds-four-known-exploited-vulnerabilities-catalog)
- [heise online: Attacks target flaws in Apache Axis and Roller, LiteLLM, Synology and more](https://www.heise.de/en/news/Attacks-target-flaws-in-Apache-Axis-and-Roller-LiteLLM-Synology-and-more-11530710.html)
- [SecurityOnline: CISA Adds 4 Exploited Flaws to KEV](https://securityonline.info/cisa-adds-4-exploited-flaws-kev-synology-litellm/)

> 注: 本セッションでは外部サイトの本文取得ができず、検索結果の要約に基づいて作成した。数値・事実は出典で再確認のこと。

---

## 関連記事

