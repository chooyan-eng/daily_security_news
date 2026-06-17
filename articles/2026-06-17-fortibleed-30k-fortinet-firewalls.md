# FortiBleed：30,000台以上のFortinet Firewallが世界194カ国で認証情報を流出

- **日付**: 2026-06-17
- **出典**: [TechCrunch](https://techcrunch.com/2026/06/17/cybercriminals-allegedly-hacked-tens-of-thousands-of-fortinet-firewalls-used-by-major-companies-all-over-the-world/) / [SOCRadar](https://socradar.io/blog/fortibleed-fortinet-firewalls-compromised/) / [Dark Reading](https://www.darkreading.com/cyberattacks-data-breaches/sweeping-credential-harvesting-heist-compromises-30k-fortinet-devices)
- **トピック**: [FortiBleed：Fortinet Firewall 大規模認証情報流出キャンペーン（2026年6月）](../topics/fortibleed-fortinet-credential-harvesting.md)
- **分類**: 新規

## 概要

SOCRadar が「FortiBleed」と命名したキャンペーンで、脅威アクターが世界194カ国の30,791台以上の Fortinet Firewall（FortiGate）を侵害し、認証情報データベースを構築していることが発覚した。銀行、通信企業、病院、政府機関、大学など幅広い組織が対象。初期侵入にはデフォルト認証情報の悪用が主要因で、侵害済みデバイスを踏み台とした再帰的な認証情報収集が行われている。

## 詳細

### FortiBleed キャンペーンの概要

| 項目 | 詳細 |
|------|------|
| キャンペーン名 | FortiBleed |
| 発見者 | SOCRadar |
| 深刻度評価 | Critical |
| 侵害デバイス数 | 30,791台以上 |
| 影響国数 | 194カ国 |
| 主要被害国 | インド、米国（全体の約1/3） |

### 攻撃手法

攻撃者の手順は体系的かつ自動化されている：

**フェーズ1: スキャンと認証情報テスト**
1. インターネット上の Fortinet デバイスをスキャン
2. 既知のデフォルト・よく使われるパスワードリストで認証試行
3. ログイン成功した認証情報をデータベースに記録

**フェーズ2: 再帰的な認証情報収集**
4. 侵害済みデバイスを「リスニングポスト」として設置
5. デバイスを通過するネットワークトラフィックを傍受
6. 傍受した新たな認証情報をスキャナーにフィードバック
7. さらに多くのデバイスを侵害（スノーボール効果）

### デフォルト認証情報問題

侵害された認証情報の大多数が**汎用管理者アカウントや Fortinet 組み込みシステムアカウント**であることが判明。これはデフォルト認証情報の変更や工場出荷時認証情報のローテーションが行われていないことを示す。

この発見は、攻撃者がブルートフォース攻撃を行う前に、デフォルト認証情報リストだけで大量のデバイスを侵害できることを意味する。

### 被害組織の種別

流出した認証情報には以下の組織が含まれる：
- 大手企業（売上高数百億ドル規模の多国籍企業）
- 銀行・金融機関
- 通信事業者
- 病院・医療機関
- 大学
- 政府機関
- エネルギー企業

### Fortinet FortiSandbox との関連

同時期に発生した FortiSandbox の CVE 悪用（CVE-2026-39813 等）と合わせて考えると、Fortinet 製品全体が積極的な攻撃キャンペーンの標的になっている状況が浮かび上がる。製品ラインが異なるものの、同じベンダーの複数製品が同時期に攻撃されている点は注目に値する。

### 推奨対応

**即時対応**:
- すべての Fortinet デバイスのデフォルト認証情報を変更
- 組み込みシステムアカウントを無効化または認証情報を強力なものに変更
- 不審なログイン試行がないかログを確認

**中長期対応**:
- 多要素認証（MFA）を全 Fortinet 管理インターフェースに適用
- FortiGate の管理インターフェースをインターネット直接公開から撤収
- SIEM での異常な認証試行の監視ルールを追加
- Fortinet 製品のファームウェアを最新版に維持

---

## 関連記事

- [Fortinet FortiSandbox 3件の重大脆弱性が野生で悪用確認](../articles/2026-06-17-fortinet-fortisandbox-active-exploitation.md) - 同時期に発覚したFortiSandbox CVEの積極的悪用
