# Dropbox、Lenovo IDのメール認証不備を突かれ約5000アカウントに不正アクセス

- **日付**: 2026-09-02
- **出典**: [BleepingComputer](https://www.bleepingcomputer.com/news/security/dropbox-accounts-breached-through-lenovo-email-verification-flaw/), [TechRadar](https://www.techradar.com/pro/security/over-5-000-dropbox-accounts-have-been-hacked-and-the-attackers-only-needed-an-email-address), [9to5Mac](https://9to5mac.com/2026/09/02/dropbox-login-breach-seemingly-caused-by-egregious-authentication-failure/)
- **トピック**: [Dropbox Lenovo ID連携認証不備によるアカウント侵害（2026年）](../topics/dropbox-lenovo-id-breach-2026.md)
- **分類**: 新規

## 概要

Dropboxは、Lenovo ID（Lenovo Identity Provider Services）のメールアドレス確認プロセスの不備を悪用され、第三者が正規ユーザーのパスワードなしでDropboxアカウントにアクセスできる状態にあったと利用者に警告した。8月4日から21日の間に約5000アカウントが不正アクセスされ、一部でファイルの閲覧・ダウンロードが行われた。

## 詳細

DropboxはLenovo Identity Provider Servicesとの連携により、確認済みのLenovo IDを使ってDropboxアカウントへログインする機能を提供している。攻撃者は、他人のメールアドレスを使って新規にLenovo IDを登録できてしまうLenovo側のメール確認プロセスの欠陥を悪用し、被害者のメールアドレスに紐づく不正なLenovo IDを作成した。

この不正に作成したLenovo IDを使うことで、攻撃者は被害者のDropboxパスワードや、メール受信箱へのアクセスを一切必要とせずに、同一メールアドレスに登録されたDropboxアカウントへログインすることが可能だった。連携認証における「メールアドレスの所有確認」という基本的な前提が崩れていたことが根本原因である。

被害範囲は2026年8月4日から8月21日の間に発生し、約5000件のDropboxアカウントが不正アクセスを受けた。このうち一部のアカウントでは、攻撃者がファイルの内容を閲覧・ダウンロードしたことが確認されている。

Dropboxは対応として、Lenovo ID経由で認証された全セッションを無効化するとともに、Lenovo ID認証を利用する際にはDropboxアカウントのパスワード入力も追加で要求する新たなログイン要件を導入した。今回の事案は、サードパーティのID連携（フェデレーテッドログイン）における認証プロバイダー側の実装不備が、連携先サービス全体のセキュリティを損なうことを示す典型例といえる。

---

## 関連記事

（本記事は新規トピックのため関連記事なし）
