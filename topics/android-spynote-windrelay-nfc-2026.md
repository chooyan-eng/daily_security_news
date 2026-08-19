# SpyNote×WindRelay：Android NFCリレー詐欺による銀行アプリ不正利用（2026年8月）

## 概要

Group-IBの研究者が、リモートアクセス型トロイの木馬 SpyNote と新型NFCリレーツール「WindRelay」を組み合わせたAndroidマルウェアキャンペーンを発見。銀行員を装った電話でSpyNoteのサイドロードを誘導し、被害者の銀行アプリを遠隔操作してローンを申請させると同時に、NFC経由でカード情報をリアルタイムに攻撃者へ中継する。

**同一性の判断に役立つ情報：**
- 発見組織: Group-IB
- マルウェア: SpyNote（RAT）＋ WindRelay（新型NFCリレーツール）
- 攻撃手法: 銀行員を装った電話でのソーシャルエンジニアリング → SpyNoteのサイドロード誘導 → 被害者の銀行アプリを遠隔操作しローン申請 → WindRelayでNFCカード情報をリアルタイム中継
- 被害内容: クレジットカード情報窃取、被害者名義でのローン不正申請
- 対象: 銀行アプリ利用者（Androidデバイス）
- マルウェア名: WindRelay（SpyNote型RATと連携）
- 攻撃手法: NFCリレー詐欺（Ghost Tap）
- 発見: Group-IB
- 検体観測期間: 2025年11月〜2026年7月（23件）
- 標的地域: チェコ・スロバキア・スロベニア（金融機関なりすまし）

## タイムライン

- [2026-08-17 WindRelay：AndroidをNFC中継器に変えリアルタイムで銀行カードを不正利用するマルウェア](../articles/2026-08-17-windrelay-android-nfc-malware.md)
- [2026-08-13 SpyNoteとNFCリレー新型ツール「WindRelay」を組み合わせたAndroid詐欺キャンペーンをGroup-IBが発見](../articles/2026-08-13-android-spynote-windrelay-nfc-fraud.md)
