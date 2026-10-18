# Warlock（Storm-2603関連）、ポルトガル語・スペイン語圏の重要インフラ等へSharePoint攻撃を継続

- **日付**: 2026-10-04
- **出典**: [Security Boulevard / 各種報道（2026-10-03）](https://securityboulevard.com/2026/10/daily-ot-security-news-october-03-2026/)
- **トピック**: [Storm-2603 SharePoint 脆弱性悪用・ランサムウェアキャンペーン（2026年）](../topics/storm-2603-sharepoint-ransomware-2026.md)
- **分類**: 続報

## 概要

中国系の関与が疑われるWarlockが、Microsoft SharePointの脆弱性を武器化し、ポルトガル語・スペイン語圏の重要インフラ、政府機関、教育機関を標的に攻撃を続けていると報じられた。

## 詳細

WarlockはStorm-2603が展開するランサムウェアとして既存トピックで追跡している。今回の報道は標的地域がラテンアメリカ・イベリア圏へ広がっている点が新しい。ブラジルでは電力、政府、教育セクターに脆弱なSharePointが露出していたとの過去の調査もある。

対策: オンプレミスSharePointへ最新パッチを適用し、公開の必要がないサーバーは外部公開を止める。ASP.NETマシンキーのローテーション、AMSI有効化、EDR導入、不審な.aspxファイルの確認を行う。

注意: 原典ページへアクセスできず、使用CVEの特定は未確認。
