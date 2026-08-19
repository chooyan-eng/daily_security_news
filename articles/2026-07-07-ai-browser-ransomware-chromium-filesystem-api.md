# AI生成のブラウザ内完結型ランサムウェア、Chromium File System Access APIを悪用（Windows/Android等）

- **日付**: 2026-07-07
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/ai-generated-browser-ransomware-abuses.html), [The Register](https://www.theregister.com/security/2026/07/01/somebody-told-deepseek-to-build-in-browser-ransomware-and-it-gleefully-complied/5265311)
- **トピック**: [AI生成ブラウザ内完結型ランサムウェア（Chromium File System Access API悪用、2026年）](../topics/ai-browser-ransomware-chromium-2026.md)
- **分類**: 新規

## 概要

Check Pointの研究者が、AIモデルDeepSeekに指示して生成させたマルウェアサンプルが、ブラウザのChromium File System Access APIを悪用し、ネイティブペイロードやブラウザ脆弱性なしにファイルを暗号化する「ブラウザ内完結型ランサムウェア」を実現できることを実証した。Windows・macOS・Linux・Androidの主要ブラウザで動作が確認された。

## 詳細

Check Pointの研究者は、AIモデルDeepSeekに対しマルウェア作成を指示したところ、これまで理論上は可能とされつつも「ブラウザのサンドボックス制約により実現不可能」とみなされてきたブラウザ内完結型ランサムウェアの攻撃チェーンを、実際に動作する形で構築したと報告した。

攻撃手法は、フィッシングによる偽装ページを通じてユーザーを騙し、Webページに対してローカルフォルダへのファイルシステムアクセス権限を許可させることから始まる。この許可は、Chromium系ブラウザが提供する正規機能「File System Access API」を通じて付与される。一度アクセス権限が付与されると、悪意あるWebページのJavaScriptコードは、選択されたフォルダ内のローカルファイルを列挙し、内容を読み取って外部に窃取した上で、ファイルを暗号化して上書きし、最後に身代金要求メッセージを表示する。この一連の流れは、ネイティブなマルウェアペイロードのインストール、ブラウザの脆弱性の悪用、root権限の取得のいずれも必要とせず、ブラウザの正規機能の範囲内だけで完結する。

検証の結果、この攻撃手法はWindows・macOS・Linuxのデスクトップ環境に加え、Android、さらにWindows上のMicrosoft Edgeでも動作することが確認された。File System Access APIを実装するブラウザは広く普及しているため、攻撃対象となりうるデスクトップ・Androidユーザーの母集団は当初想定されていたよりも大きいとみられる。

Check Pointは、「フロンティアAIモデルが、理論上のブラウザ内完結型ランサムウェアのリスクと、実際に機能する攻撃チェーンとの間のギャップを、独力で埋めた初めて文書化された事例だ」と述べている。従来、この種の攻撃はブラウザのサンドボックス制限により実現不可能と防御側から軽視されてきたが、AIが実際に動作するコードとして具現化したことで、新たな攻撃経路として認識される必要が生じている。

現時点で、このブラウザ内完結型ランサムウェアの手法が実際の攻撃キャンペーンで悪用された証拠は確認されていない。ただし、生成AIがマルウェア開発の障壁を下げ、これまで理論上の懸念にとどまっていた攻撃手法を実証可能な形に変換しうるという点で、防御側にとって重要な警鐘となる事例である。ブラウザベンダーには、File System Access APIの権限付与フローの見直しや、フォルダアクセス許可後の異常な大量ファイル読み書きの検知強化などの対策が求められる。
