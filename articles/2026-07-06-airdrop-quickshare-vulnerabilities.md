# AirDropとAndroid Quick Shareに6件の脆弱性 – 近接する攻撃者が数十億台のデバイスをクラッシュ・改ざん可能

- **日付**: 2026-07-06
- **出典**: [The Hacker News](https://thehackernews.com/2026/06/airdrop-and-quick-share-flaws-let.html)
- **トピック**: [AirDrop・Quick Share 近接ファイル共有プロトコル脆弱性（2026年）](../topics/airdrop-quickshare-vulnerabilities-2026.md)
- **分類**: 新規

## 概要

AppleのAirDropとGoogle/SamsungのQuick Shareに合計6件のセキュリティ脆弱性が発見された。近接無線を悪用し、10〜30メートル圏内の攻撃者がサービスクラッシュや転送内容の改ざんを引き起こせる。世界で約50億台のiPhone・Android端末が影響を受けるとされ、一部は修正済み、一部は協調開示中。

## 詳細

### 脆弱性の概要

研究者らはAirDropとQuick Shareの近接ファイル共有プロトコルに計6件の脆弱性を発見した。攻撃者は対象デバイスの通常利用範囲内（10〜30メートル）にいるだけで攻撃を成立させられ、混雑した環境では1人の攻撃者が同時に数百台のデバイスへ影響を及ぼし得る。

### AirDrop側の3件

3件のAirDropの脆弱性はいずれも、macOS/iOSでAirDropを処理するバックグラウンドサービス「sharingd」のクラッシュに帰結する。sharingdはAirDropだけでなくAirPlay・Handoff・Universal Clipboard・Continuity Camera・NameDropも担っているため、1つのクラッシュでこれら全機能が同時に停止する。うち1件は単一のHTTP POSTリクエストのみでsharingdを即座に停止させられる。

### Quick Share側の2件

Samsung Quick Shareでは、セキュアなセッションを確立するハンドシェイクをスキップできる脆弱性が2件確認された。1つは暗号化確立前に未検証のデバイスが接続を主導できてしまうもの、もう1つはセキュアセッション確立後も一部の制御メッセージが平文のまま通過してしまうものである。

### ベンダーの対応状況

Appleは3件のうち1件について既にパッチを提供しCVE番号を割り当てたが、アドバイザリはまだ非公開。残り2件は協調開示のプロセス中。Googleは（Windows向けの実装の）脆弱性に対して報奨金を支払い、コード修正を完了しているが、CVE番号は未確定。

### リスクと対策

いずれの脆弱性も現時点でリモートコード実行の確証はなく、サービス拒否（DoS）や転送の乗っ取り・改ざんが主な影響とされる。ユーザーは各社のOSアップデートを速やかに適用し、不要な時はAirDrop/Quick Shareの受信設定を「すべての人」から「連絡先のみ」等に制限することが推奨される。

---

## 関連記事

なし（新規トピック）
