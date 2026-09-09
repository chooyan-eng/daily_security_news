# 「PREY-0058」ITヘルプデスク偽装ビッシングによるMicrosoft 365侵害（2026年）

## 概要

Arctic Wolfが追跡する攻撃クラスター「PREY-0058」。社内ITヘルプデスクを装った電話（ビッシング）で企業幹部を偽の認証ポータルへ誘導し、窃取したセッショントークンを住宅用プロキシ経由で再生してMFAを実質回避、Microsoft 365等SaaS環境からデータを窃取・恐喝する。Google Threat Intelligence Groupが「UNC6671」と呼ぶ恐喝クラスター（別名BlackFile、Pink、Helix、Cinder、Redact）とTTPの類似性が指摘されている。

**同一性の判断に役立つ情報：**
- 攻撃クラスター名: PREY-0058（Arctic Wolf命名）
- 関連クラスター: UNC6671（Google Threat Intelligence Group）、別名BlackFile/Pink/Helix/Cinder/Redact
- 標的: 企業の取締役・副社長クラスの経営幹部
- 手口: ITヘルプデスク偽装の電話→偽認証ポータル誘導→セッショントークン窃取→住宅用プロキシ経由での再生によるMFA実質回避
- 標的サービス: Microsoft 365（SharePoint、OneDrive、Exchange）、Box等
- 攻撃後: データ収集後に金銭要求（恐喝）

## タイムライン

- [2026-09-08 偽装ITヘルプデスクの電話で幹部を騙しMicrosoft 365を乗っ取る「PREY-0058」キャンペーン](../articles/2026-09-08-prey-0058-helpdesk-vishing-m365.md)
