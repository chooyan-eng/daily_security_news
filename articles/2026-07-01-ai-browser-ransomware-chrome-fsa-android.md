# AI生成のブラウザ完結型ランサムウェア、ChromeのFile System Access APIをAndroidで悪用

- **日付**: 2026-07-01
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/ai-generated-browser-ransomware-abuses.html)
- **トピック**: [ブラウザ完結型ランサムウェア（File System Access API悪用、2026年）](../topics/browser-native-ransomware-fsapi-2026.md)
- **分類**: 新規

## 概要

Check Point Research は、生成AI（DeepSeek）が独自に考案した、ブラウザ内で完結するランサムウェア攻撃手法を発見した。Chrome の File System Access API（`showDirectoryPicker()`）を悪用し、Windows・Android両方で動作する。特に Android では DCIM（写真）フォルダへのアクセスが可能で、ユーザーの許可さえ得られれば端末内ファイルの暗号化・恐喝が実行できる。

## 詳細

### 発見の経緯

Check Point Research は、VirusTotal にアップロードされた `deepseek_python_20260125_da0631.py` という名称の Python Flask アプリケーションを分析した結果、これが「完全に機能する情報窃取・ランサムウェアツールキット」であることを確認した。このコードは生成AI（DeepSeek）によって作成されたと見られ、従来「ブラウザのサンドボックス制限により実現不可能」とされてきたブラウザ完結型ランサムウェアの概念を、実際に動作する攻撃チェーンへと具体化した点で注目に値する。

### 攻撃の仕組み

1. フィッシングのおとりページを通じて被害者を誘導し、Webページに対しファイルシステムへのアクセス権限を付与させる。
2. 正規のブラウザAPIである `showDirectoryPicker()` を呼び出し、選択されたフォルダ内のファイルを列挙。
3. ファイルの内容を読み取り、外部へ窃取（exfiltration）。
4. ファイルを暗号化して上書き。
5. 最終的に恐喝メッセージを被害者に表示。

このプロセスはすべてブラウザ内のJavaScriptのみで完結し、従来型のマルウェア実行ファイルを必要としない。

### Androidが特に懸念される理由

Android の DCIM（写真）フォルダは個人の高価値データの宝庫であり、iOSとは異なり、モダンな Android 版 Chrome はユーザーの承認後にこれらのフォルダへの読み書きアクセスを許可する File System Access API を公開している。Chrome 132 で Android 向けの File System Access のフルサポートが導入されており、Check Point の検証では Chrome 148 においてWebページが DCIM フォルダへのアクセスを要求できることが確認された。

### 意義

これは、フロンティアAIモデルが「理論上のブラウザ完結型ランサムウェアのリスク」と「実際に動作する攻撃チェーン」の間のギャップを、独力で埋めた初めての実証事例とされる。防御側がブラウザのサンドボックス制限により実現不可能と見なしていた攻撃パスを、AIが偶然（あるいは意図的に）明らかにした形となる。

### 対策

- ブラウザからの予期しないファイルシステムアクセス要求への警戒（フィッシングページでの許可付与を避ける）
- モバイル端末の重要フォルダ（写真等）の定期的なバックアップ
- 企業・組織においてブラウザの File System Access API の利用ポリシーの見直し
- エンドポイント・モバイルセキュリティ製品におけるブラウザ内アクティビティの監視強化

---

## 関連記事

なし
