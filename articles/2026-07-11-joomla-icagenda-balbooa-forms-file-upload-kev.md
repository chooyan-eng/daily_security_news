# CISA、Joomla拡張機能iCagenda・Balbooa Formsの未認証ファイルアップロード脆弱性2件をKEVに追加

- **日付**: 2026-07-11
- **出典**: [CISA](https://www.cisa.gov/news-events/alerts/2026/07/10/cisa-adds-two-known-exploited-vulnerabilities-catalog), [windowsnews.ai](https://windowsnews.ai/article/two-joomla-extensions-under-active-attack-cisa-orders-agencies-to-patch-file-upload-flaws.436686)
- **分類**: 新規

## 概要

CISAは2026年7月10日、Joomla向け拡張機能であるイベント管理コンポーネント「iCagenda」（CVE-2026-48939）とフォーム作成コンポーネント「Balbooa Forms」（CVE-2026-56291）に存在する、いずれもCVSS 9.8の危険なファイルタイプの無制限アップロード脆弱性を、積極的悪用の証拠があるとしてKnown Exploited Vulnerabilities（KEV）カタログに追加した。連邦機関はBOD 26-04に基づき優先的な修正が求められる。

## 詳細

### CVE-2026-48939（iCagenda）

iCagendaはJoomla向けのイベント管理・カレンダーコンポーネントで、バージョン4.0.7以前に危険なファイルタイプの無制限アップロード脆弱性が存在する。攻撃者はイベント登録機能などを通じて悪意あるファイル（PHPファイル等）をアップロードし、Webサーバー上でリモートコード実行を達成できる。修正版は3.9.13以降で提供されている。

### CVE-2026-56291（Balbooa Forms）

Balbooa Formsはフォーム添付ファイル処理に関わるアップロードハンドラーに脆弱性があり、リクエストのMIMEタイプおよびファイル拡張子を操作することでファイルタイプ制限を回避できる。バージョン2.2.3未満が影響を受ける、未認証のファイルアップロードによるRCEの脆弱性である。

### 脆弱性クラスの共通性

両脆弱性はいずれも「Unrestricted Upload of File with Dangerous Type」（危険なファイルタイプの無制限アップロード）に分類され、Joomlaエコシステムにおいて頻発している脆弱性クラスである。同種の脆弱性は本リポジトリで既に追跡している[Joomla JCE CVE-2026-48907](../topics/joomla-jce-cve-2026-48907.md)（Widget Factory JCEコンポーネントの不適切なアクセス制御によるPHPファイルアップロード、CVSS 10.0、2026年6月にKEV追加）とも攻撃パターンが酷似しており、Joomlaサードパーティ拡張機能全般に対するファイルアップロード検証不備の悪用が継続的なトレンドとなっていることを示している。

### 対応状況

CISAはBOD 26-04（旧BOD 22-01を置き換えた指令で、深刻度と悪用状況に応じて可変の修正期限を設定）に基づき、連邦機関に優先的なパッチ適用を求めている。両CVEとも公開されているエクスプロイトコードが存在するとみられ、外部に公開されたJoomlaサイトの管理者は直ちにバージョン確認とアップデートを行う必要がある。

## 対策・推奨事項

- iCagendaを3.9.13以降、Balbooa Formsを2.2.3以降に更新する
- アップロードディレクトリでのスクリプト実行を無効化するWebサーバー設定を検討する
- WAF（Webアプリケーションファイアウォール）でファイルアップロードパターンを監視する

---

## 関連記事

- [Joomla JCEプラグイン CVE-2026-48907（CVSS 10.0）がCISA KEVに追加・PHPコード実行に悪用](../articles/2026-06-17-joomla-jce-cve-2026-48907-cisa-kev.md) - 同じくJoomla拡張機能のファイルアップロード検証不備を突いたRCE脆弱性で、攻撃パターンが類似
