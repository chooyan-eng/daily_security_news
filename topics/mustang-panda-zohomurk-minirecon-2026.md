# Mustang Panda：Zoho WorkDrive 悪用 ZOHOMURK・MINIRECON キャンペーン（2026年）

## 概要

中国系APTグループ「Mustang Panda」が、正規クラウドストレージサービス「Zoho WorkDrive」をC2チャネルとして悪用する2つの並行キャンペーンを展開。新型マルウェア「ZOHOMURK」（Zoho OAuth資格情報を使いWorkDriveをデッドドロップ化）と「MINIRECON」（Toneshellバックドアの改変版、WebSocket over HTTPSでビーコニング）を使用し、インドの水力発電セクターおよび対台湾協力関係のある政府機関を標的とする。Acronis Threat Research Unitが発見。

**同一性の判断に役立つ情報：**
- 脅威アクター: Mustang Panda（中国系APT、Acronisが高確度で帰属）
- マルウェア: ZOHOMURK（Zoho WorkDrive悪用C2）、MINIRECON（Toneshell改変版）
- 悪用された正規サービス: Zoho WorkDrive
- 標的: インド政府機関（水力発電セクター、対台湾MOU関連部門）
- 配信手法: スピアフィッシング、ZIPアーカイブ＋隠しDLL
- 発見: Acronis Threat Research Unit

## タイムライン

- [2026-06-30 中国系APT「Mustang Panda」、Zoho WorkDriveを指令チャネルに悪用しインド政府機関を攻撃](../articles/2026-06-30-mustang-panda-zohomurk-minirecon.md)
