# GodDamnランサムウェア・PoisonXドライバ（2026年）

## 概要

2026年5月21日に初確認された新興ランサムウェア「GodDamn」が、2026年4月7日にGitHub上で公開された署名済み脆弱ドライバ「PoisonX」をBYOVD手法で悪用しEDR等のセキュリティ製品を無効化していることが判明。PsExecによる横展開、NirSoftツールキットによる認証情報窃取も併用。米企業を主な標的とする。

**同一性の判断に役立つ情報：**
- ランサムウェアファミリー名: GodDamn（既存グループのリブランドとみられる）
- 初確認日: 2026年5月21日
- 悪用ドライバ: PoisonX（署名済みカーネルドライバ、2026年4月7日にGitHub公開、以前CrowdStrike Falcon停止に悪用された実績あり）
- 手法: BYOVD（Bring Your Own Vulnerable Driver）によるEDR無効化、PsExecによる横展開、NirSoftツールキットによる認証情報窃取
- 主な標的: 米国企業

## タイムライン

- [2026-07-09 「GodDamn」ランサムウェア、署名済みカーネルドライバ「PoisonX」でEDRを無効化](../articles/2026-07-09-goddamn-ransomware-poisonx-driver.md)
