# Dropbox Lenovo ID連携認証不備によるアカウント侵害（2026年）

## 概要

Lenovo Identity Provider Services（Lenovo ID）のメールアドレス確認プロセスの不備を悪用し、攻撃者が他人のメールアドレスで不正にLenovo IDを登録、そのIDを使ってDropboxアカウントへパスワードなしで不正ログインした事案。2026年8月4日〜21日の間に約5000アカウントが被害を受けた。

**同一性の判断に役立つ情報：**
- 対象サービス: Dropbox（Lenovo ID経由のフェデレーテッドログイン機能）
- 根本原因: Lenovo Identity Provider Servicesのメールアドレス確認プロセスの不備
- 被害期間: 2026年8月4日〜8月21日
- 被害規模: 約5000アカウント
- 被害内容: 一部アカウントでファイルの閲覧・ダウンロード
- 公表日: 2026年9月2日
- 対応: Lenovo ID経由セッションの全無効化、Lenovo ID認証利用時のDropboxパスワード入力必須化

## タイムライン

- [2026-09-02 Dropbox、Lenovo IDのメール認証不備を突かれ約5000アカウントに不正アクセス](../articles/2026-09-02-dropbox-lenovo-id-account-breach.md)
