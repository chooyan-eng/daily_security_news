# 「GodDamn」ランサムウェア、署名済みカーネルドライバ「PoisonX」でEDRを無効化

- **日付**: 2026-07-09
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/goddamn-ransomware-uses-poisonx-driver.html)
- **トピック**: [GodDamnランサムウェア・PoisonXドライバ（2026年）](../topics/goddamn-ransomware-poisonx-2026.md)
- **分類**: 新規

## 概要

2026年5月21日に初確認された新興ランサムウェアファミリー「GodDamn」が、BYOVD（Bring Your Own Vulnerable Driver）手法により署名済みカーネルドライバ「PoisonX」を悪用し、セキュリティ製品を無効化していることが明らかになった。PoisonXは2026年4月にGitHub上で公開されたツールで、以前にはCrowdStrike Falconサービスの強制停止に使われた実績がある。米企業を主な標的としている。

## 詳細

GodDamnは既存のランサムウェアグループの「リブランド」とみられており、防御回避（Defense Evasion）の手口として、正規の署名を持つが脆弱性のあるカーネルドライバを悪用してカーネル権限でのコード実行を行うBYOVD手法を採用している。使用されるドライバ「PoisonX」は2026年4月7日にGitHub上で公開されたツールで、公開当初からエンドポイントセキュリティ製品のプロセスを強制終了させる目的での悪用が懸念されていた。実際、PoisonXは早期の段階でCrowdStrike Falconサービスを停止させる攻撃に使われたことが確認されている。

GodDamnの攻撃チェーンでは、正規のリモート管理ツールであるPsExecを用いた横展開（ラテラルムーブメント）と、認証情報窃取のためのNirSoftツールキットの利用も報告されている。署名済みドライバを利用することで、Windowsのドライバ署名強制（Driver Signature Enforcement）機構を正面から突破する必要がなく、カーネルレベルでEDR（Endpoint Detection and Response）製品のプロセスやドライバを直接無効化・改ざんすることが可能になる。

BYOVD手法自体は既知の攻撃パターンだが、GodDamnの事例は「一般公開されたレッドチーム/攻撃検証ツールが、公開後わずか1ヶ月半程度で実際のランサムウェアキャンペーンに転用される」速度の速さを示す事例として注目されている。企業は、既知の脆弱なドライバのハッシュ・証明書をブロックリストに登録するMicrosoftのVulnerable Driver Blocklist等の対策を最新の状態に保つとともに、PsExecなど正規の管理ツールの不審な利用を検知する監視体制の強化が求められる。
