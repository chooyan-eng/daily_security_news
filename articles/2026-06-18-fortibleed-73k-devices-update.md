# FortiBleed 続報：侵害デバイス数が73,932台に拡大、規模が倍増と判明

- **日付**: 2026-06-18
- **出典**: [Help Net Security](https://www.helpnetsecurity.com/2026/06/18/fortinet-fortibleed-data-leak/), [HKCERT](https://www.hkcert.org/security-bulletin/security-alert-fortibleed-credential-leak-incident-over-70-000-fortinet-devices-suspected-to-be-affected-by-data-and-credential-exposure-hong-kong-organisations-may-be-affected_20260618), [BleepingComputer](https://www.bleepingcomputer.com/news/security/fortibleed-leak-exposes-fortinet-vpn-credentials-for-73-000-devices/)
- **トピック**: [FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）](../topics/fortibleed-fortinet-credential-harvesting.md)
- **分類**: 続報

## 概要

FortiBleedキャンペーンの最新分析で、世界194カ国で侵害された Fortinet FortiGate デバイスが当初推定の3万台超から73,932台へと倍以上に拡大していることが明らかになった。香港コンピュータ緊急対応チーム（HKCERT）も6月18日に地域組織への影響を警告する緊急セキュリティアラートを発出した。

## 詳細

### 規模の再評価

当初の報告では侵害デバイス数が30,791台以上とされていたが、6月18日時点の詳細分析により73,932台のユニークな FortiGate デバイスのプレーンテキスト認証情報（ユーザー名・メール・パスワード）が漏洩していることが確認された。影響範囲は194カ国・2万1000以上のドメインにおよぶ。

### 流出データの内容

漏洩したデータセットには以下が含まれる：
- Fortinet FortiGate Firewall/VPN デバイスのプレーンテキスト認証情報（ユーザー名・メール・パスワード）
- Oracle、Chevron、Lenovo、FedEx、Foxconn、Samsung、Comcast、Siemens、PwC、Accenture 等の大手企業も含む

### 攻撃の手口

ロシア語話者のサイバー犯罪グループが過去の Fortinet 侵害ダンプやインフォスティーラーマルウェアのログから認証情報を収集し、到達可能なすべての FortiGate デバイスに対して自動的に試行。32万以上のターゲットに対し約11億6000万回の認証試行が実施され、成功したログインが記録された。このデータは当初攻撃者のサーバーに誤って公開され、セキュリティ研究者 Volodymyr "Bob" Diachenko が発見した。

### Fortinet の見解

Fortinet は「このデータは過去のインシデントのデータを再共有したものと、認証情報のブルートフォース攻撃によるものであり、最近のインシデントやアドバイザリとは無関係」と説明しているが、認証情報の有効性については否定していない。

### HKCERT の勧告

香港コンピュータ緊急対応チーム（HKCERT）は2026年6月18日にセキュリティアラートを発出し、香港の組織も影響を受けている可能性があるとして、対象 IP アドレスリストとの照合と即時のパスワード変更を推奨している。

### 推奨対応

1. 自組織の FortiGate デバイスの IP アドレスが漏洩データセットに含まれているか確認
2. 全 FortiGate デバイスの認証情報を即時変更
3. MFA を未設定のデバイスには設定を実施
4. 異常なログイン試行・設定変更の痕跡を調査
5. Fortinet の最新セキュリティアップデートを適用

---

## 関連記事
