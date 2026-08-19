# Ruby on Rails Active Storage に重大な任意ファイル読み取り・RCE脆弱性「KindaRails2Shell」（CVE-2026-66066）

- **日付**: 2026-08-03
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/08/03/kindarails2shell-cve-2026-66066-vulnerability/)
- **トピック**: [Ruby on Rails Active Storage CVE-2026-66066「KindaRails2Shell」](../topics/rails-active-storage-cve-2026-66066.md)
- **分類**: 新規

## 概要

Ruby on Railsの画像アップロード機能「Active Storage」に、libvipsとの組み合わせ利用時に悪用可能な重大な脆弱性（CVE-2026-66066、CVSS 9.5）が公開された。攻撃者は細工した画像ファイルをアップロードするだけで任意のサーバーファイルを読み取ることができ、secret_key_baseなどの機密情報の窃取を通じてリモートコード実行（RCE）にまで発展し得る。7月29日に公開されたのち、8月に入っても被害範囲の広さから継続して報道されている。

## 詳細

### 脆弱性の技術的詳細

**CVE**: CVE-2026-66066（通称「KindaRails2Shell」）
**CVSS**: 9.5（Critical）
**影響コンポーネント**: Active Storage（libvipsを画像処理エンジンとして使用する構成）
**影響バージョン**: Active Storage 7.2.3.2 より前、8.0.x は 8.0.5.1 より前、8.1.x は 8.1.3.1 より前

Active StorageがlibvipsをバックエンドとしてEXIF回転补正やサムネイル生成などの画像処理を行う際、ユーザーがアップロードした画像に対する検証が不十分であるため、攻撃者は特別に細工した画像ファイルをアップロードすることでサーバー上の任意のファイルを読み取ることができる。libvipsが未信頼の入力を処理する過程を悪用する手法であり、信頼できないユーザーからの画像アップロードを受け付けるRailsアプリケーションが広く影響を受ける。

### 影響の深刻度

読み取り可能なファイルには、Railsプロセスの環境変数や以下のような機密情報が含まれ得る。

- `secret_key_base`（Railsのセッション署名・暗号化鍵）
- Rails master key
- データベースパスワード
- クラウドストレージの認証情報・APIトークン

これらの情報が漏洩した場合、攻撃者はセッション偽造やリモートコード実行、さらには接続先システムへの横展開が可能になるとされる。

### 対策

Active Storageを使用し、かつlibvipsで画像処理を行っているアプリケーションの管理者は、修正済みバージョンへのアップグレードに加え、libvips自体を8.13以降にアップデートする必要がある。RailsまたはActive Storageのみを更新し、古いバージョンのlibvipsを使い続けている場合は脆弱性が残る点に注意が必要である。

---

## 関連記事

なし（新規トピック）
