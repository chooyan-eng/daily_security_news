# ASOSアプリから「ASOS HACKED」の不正プッシュ通知、Snowflake侵害を主張し恐喝

- **日付**: 2026-10-06
- **出典**: [BleepingComputer／Malwarebytes／IT Security Guru](https://www.bleepingcomputer.com/news/security/asos-confirms-data-breach-after-hacked-in-app-notifications/)
- **トピック**: [ASOS公式アプリ不正プッシュ通知・Snowflake侵害主張（2026年10月）](../topics/asos-app-push-extortion-2026.md)
- **分類**: 新規

## 概要

英ファッション小売ASOSは10月6日、同社モバイルアプリから第三者が不正なプッシュ通知を送信し、Snowflake環境を完全に侵害したと主張した件で、データ侵害を認めた。顧客との連絡に使うサードパーティ基盤が不正アクセスされたとしている。

## 詳細

- 10月6日午前（英国時間約10時）、多数の利用者に「ASOS HACKED」と題する通知が届いた。本文は「ASOSのDPOとITへ。Snowflakeインスタンスを完全に侵害した。交渉に応じなければ公開する」という趣旨で、Telegramチャンネルへのリンクを含んでいた。複数国の利用者が受信したと報じられている。
- ASOSは、顧客との連絡に用いるサードパーティのプラットフォームが不正アクセスを受けたことを認め、氏名・連絡先などの基本的な個人情報が漏えいした可能性があるとしている。Snowflake環境侵害という攻撃者の主張自体や影響人数は未確認。
- 報道では、攻撃者は新興グループ「XuanyeGroup」と関連づけられ、KELAの調査ではRoblox・Counter-Strikeの高額ゲーム内資産を使った資金洗浄を試みていたとされる。
- 技術的示唆：プッシュ通知配信基盤（CRM/通知SaaSの管理画面・APIキー）の認証情報が窃取された可能性があり、アプリ本体の改ざんではなくバックエンドの委託先連携が弱点になり得る。株価は通知直後30分で約5%下落したと報じられた。
- 対策：通知・マーケティング基盤のAPIキーのローテーション、MFA、IP制限、送信権限の分離。利用者は通知内リンクを開かないこと。
- 出典：[Malwarebytes](https://www.malwarebytes.com/blog/news/2026/10/asos-hackers-send-push-notifications-to-customers)、[IT Security Guru](https://www.itsecurityguru.org/2026/10/06/asos-app-turned-into-ransom-note-as-hackers-claim-snowflake-breach/)

---

## 関連記事


