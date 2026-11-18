# COLD RELIC（Star Blizzard）によるクラウドID連鎖侵害（2026年11月公表）

## 概要

GoogleのMandiantおよびThreat Intelligence Groupが2026年11月17日に公開した、ロシア系スパイ集団COLD RELIC（別名Star Blizzard）によるクラウドID侵害の連鎖事例。

**同一性の判断に役立つ情報：**
- アクター: COLD RELIC（Star Blizzard）
- 第1侵害（2025年後半）: Google Workspace Super Adminアカウントを窃取認証情報＋MFA誤承認で侵害、Customer Takeoutで全データ持ち出し
- 第2侵害（2026年）: 第1被害組織の従業員になりすまし、Entra IDの認証情報・トークンをフィッシング。新規MFAデバイス登録で持続化
- 検知指標: CUSTOMER_TAKEOUT_CREATEDイベント
- 被害組織名は非公表（いずれも米国組織）

## タイムライン

- [2026-11-18 ロシア系COLD RELIC、Google Workspaceから窃取した情報を足がかりに別の米国組織を侵害 Google/Mandiantが事例公開](../articles/2026-11-18-cold-relic-google-workspace-chained-intrusion.md)
