# 中国系APT、Chrome/Windowsゼロデイ連鎖でNGOを標的に「GRIMWEDGE」を展開

- **日付**: 2026-09-20
- **出典**: [The Hacker News](https://thehackernews.com/2026/09/china-linked-hackers-exploit-chrome.html), [Volexity](https://www.volexity.com/blog/2026/09/09/mind-the-patch-gap-multiple-chinese-threat-actors-chain-0-day-exploits-in-chrome-windows/)
- **トピック**: [UTA0560/APT31 Chrome-Windowsゼロデイ連鎖攻撃「GRIMWEDGE」NGO標的キャンペーン（2026年9月）](../topics/grimwedge-china-chrome-windows-zeroday-chain-2026.md)
- **分類**: 新規

## 概要

中国系脅威アクター「UTA0560」が、2026年9月1日に複数のNGOへ標的型メールを送付し、米大学サイトの反射型XSS脆弱性を悪用してChrome/Windowsの脆弱性3件を連鎖させるエクスプロイトチェーンへ誘導、マルウェア「GRIMWEDGE」を展開した。同一チェーンはAPT31による「LONGTALE」展開にも使われており、Chromiumの修正が安定版Chromeへ未反映の「パッチギャップ」を突いた攻撃と分析されている。

## 詳細

Volexityが「BlueMoon」と名付けたこのキャンペーンでは、攻撃者はまずNGO関係者にフィッシングメールを送付し、正規の米大学ウェブサイトへのリンクをクリックさせる。このリンクは当該大学サイトに存在する反射型クロスサイトスクリプティング（XSS）脆弱性を悪用しており、被害者を攻撃者管理下のインフラへリダイレクトさせ、多段階のエクスプロイトチェーンを実行させる。

エクスプロイトチェーンは3つの脆弱性で構成される。まずCVE-2026-85046（Chrome V8のtype confusion）によりV8サンドボックス内での任意読み書きを獲得し、次にCVE-2026-87491を用いてブラウザのサンドボックスを脱出、最後にWindowsのAdvanced Local Procedure Call（ALPC）に存在するCVE-2026-85880を悪用してChromeブラウザプロセスへコードを注入し、任意コード実行を達成する。これら3件はいずれもGoogleおよびMicrosoftによって既に修正済みだが、攻撃者はオープンソースのChromiumコードベースでは修正済みでも安定版Chromeへの反映が遅れる「パッチギャップ」の期間を突いて、実質的なゼロデイとして悪用した。

展開されるマルウェア「GRIMWEDGE」は、ホスト情報の偵察、ファイル・プロセス管理、コマンド実行、追加ペイロードの配信といった機能を備えるバックドアである。同じエクスプロイトチェーンは、別の中国系脅威アクターであるAPT31が「LONGTALE」というマルウェアを展開する際にも使用されており、複数の中国系グループが同一のパッチギャップ攻撃基盤を共有している可能性が指摘されている。

本件は、ブラウザ・OS双方のパッチ適用が完了していても、Chromiumのオープンソースコミットから安定版ブラウザへの反映までのタイムラグそのものが攻撃対象になり得ることを示す事例であり、また正規サイトの反射型XSSが標的型攻撃の初期導線として悪用される典型例でもある。組織は自社Webサイトの反射型XSS対策とあわせて、ブラウザの自動更新設定の徹底が求められる。
