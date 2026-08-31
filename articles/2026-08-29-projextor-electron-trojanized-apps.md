# 偽装生産性アプリ「Projextor」、Electronフレームワークを悪用しマルウェアを隠蔽

- **日付**: 2026-08-29
- **出典**: [Cyber Security News](https://cybersecuritynews.com/projextor-shows-malware/), [GBHackers](https://gbhackers.com/projextor-infection-technique/), [Cyberpress](https://cyberpress.org/projextor-abuses-electron-framework/)
- **トピック**: [Projextor トロイの木馬化Electronアプリキャンペーン（2026年）](../topics/projextor-electron-trojanized-apps-2026.md)
- **分類**: 新規

## 概要

セキュリティ企業G DATAが、ドキュメント変換ツールや献立プランナーなど、一見有用なデスクトップアプリケーションを装いながら悪性コードを隠すマルウェアクラスター「Projextor」を確認した。クロスプラットフォームのElectronフレームワークを悪用し、正規機能の裏でリモートからのJavaScript実行やデスクトップキャプチャなどの監視機能を仕込んでいる。

## 詳細

Projextorは、無料の生産性ソフトウェアを謳う偽の配布サイトやインストーラーを通じて拡散する。ユーザーがインストーラーを実行すると、Electronベースのアプリケーションが取得され、ファイルを開く・出力を保存するといった見た目上正規の動作の裏で、有害な挙動を紛れ込ませる仕組みになっている。G DATAのアナリストは、同じ隠しフレームワークを共有するドキュメント変換ツール、食事プランナー、レシピアプリなど複数のアプリ群からなるクラスターを特定しており、確認された具体的なアプリ名には「Kitchen Canvas」「Food Formula」「DocConvertWizard」「PDF Grip」などが含まれる。

技術的に注目される点は、Projextorのコードが`contextIsolation: false`を明示的に設定していることである。コンテキスト分離はElectron 12以降デフォルトで有効化されており、Webコンテンツを読み込むアプリケーションにおける中核的なセキュリティ推奨事項とされているが、Projextorはこれを意図的に無効化することで、レンダラープロセスとNode.js環境の境界をなくし、任意のJavaScriptをより自由に実行できる状態を作り出している。

これらのアプリは広告どおりの実用機能（PDF変換、献立作成など）を確かに提供する一方で、共有された悪性コードベースにより、実行時のJavaScript実行やデスクトップキャプチャ機能へのアクセスも可能となっており、深刻な監視・侵害後活動のリスクをもたらす。正規のオープンソース技術（Electron）を土台にした偽装アプリがマルウェア配布の隠れ蓑として利用される事例は近年増加傾向にあり、フリーソフトのダウンロード元を慎重に確認することの重要性を改めて示している。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
