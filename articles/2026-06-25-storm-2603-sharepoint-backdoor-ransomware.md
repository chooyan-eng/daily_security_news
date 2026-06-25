# Storm-2603 が未修正 SharePoint サーバーを悪用：ランサムウェアとカスタムバックドア「Project AK47」を展開

- **日付**: 2026-06-25
- **出典**: [CybersecurityNews](https://cybersecuritynews.com/hackers-exploit-unpatched-sharepoint-servers/)
- **トピック**: [Storm-2603 SharePoint 脆弱性悪用・ランサムウェアキャンペーン（2026年）](../topics/storm-2603-sharepoint-ransomware-2026.md)
- **分類**: 新規

## 概要

脅威アクター Storm-2603 が、未修正のオンプレミス SharePoint サーバーを標的に少なくとも2025年半ばから攻撃を継続していることが Microsoft の調査で判明した。CVE-2025-49706 等の既知脆弱性を悪用し、正規フォレンジックツール・Cloudflare トンネル・BYOVD 手法を組み合わせて侵入を深め、独自ツールセット「Project AK47」（バックドア・ランサムウェア・ローダーを含む）を展開する。

## 詳細

### 悪用された脆弱性

Storm-2603 が利用した SharePoint 関連 CVE：

| CVE | 種別 | 内容 |
|-----|------|------|
| CVE-2025-49706 | RCE | SharePoint Server 認証前リモートコード実行 |
| CVE-2025-49704 | RCE | SharePoint Server 認証前リモートコード実行（別経路） |
| CVE-2025-11371 | LFI | 未認証ローカルファイルインクルード（機微なシステムファイルへのアクセス） |

### 攻撃手順

**1. 初期アクセス**  
公開済み CVE を悪用してオンプレミス SharePoint サーバーに未認証で侵入。ただし CVE-2025-49706/49704 のパッチ公開後も未適用のサーバーが標的となっている。

**2. 偵察・横展開**  
正規フォレンジックツール「Velociraptor」を SYSTEM 権限で実行し、環境のマッピングとデータ収集を実施。Cloudflare トンネル・Zoho Assist（リモート管理）・Visual Studio Code による SSH ベース C2 接続など、複数のリモートアクセス経路を確立する。

**3. セキュリティ無効化（BYOVD）**  
脆弱なドライバー `NSecKrnl.sys` を悪用した「Bring Your Own Vulnerable Driver（BYOVD）」攻撃でカーネルレベルアクセスを取得し、システムメモリを改ざんしてエンドポイント保護ツールを無効化する。

**4. Project AK47 展開**  
独自ツールセット「Project AK47」を展開：
- **バックドア**: 長期的な持続的アクセスを維持
- **ランサムウェア**: 暗号化ファイルに `.x2anylock` 拡張子を付与。タイムスタンプベースのキルスイッチ（システム日付が 2026年6月6日以降の場合は実行終了）を持つ
- **ローダー**: 追加マルウェアの読み込みに使用

### 並行攻撃の発見

Microsoft の調査では、同一の SharePoint サーバーに **2つの独立した脅威アクター**が並行して侵入している事例が確認された（互いの存在を認識せずに同じ被害者環境を利用）。

### 中国系 APT との関連

Palo Alto Networks Unit 42 の「Project AK47」調査では、このツールセットを使用する活動クラスター「CL-CRI-1040」が中国系脅威アクターの戦術・手法と一致する要素を持つと指摘している。ただし帰属は暫定的。

### 対策推奨

- CVE-2025-49706、CVE-2025-49704、CVE-2025-11371 の即時パッチ適用
- オンプレミス SharePoint への外部公開を最小化
- BYOVD 対策：脆弱なドライバーブロックリストの適用（Microsoft Vulnerable Driver Blocklist）
- Cloudflare トンネルや VSCode SSH の異常利用を監視

---

## 関連記事

なし（新規トピック）
