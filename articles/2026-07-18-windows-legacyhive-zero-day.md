# 「LegacyHive」：Windows User Profile Serviceを悪用する特権昇格ゼロデイがPatch Tuesday直後に公開

- **日付**: 2026-07-18
- **出典**: [The Hacker News](https://thehackernews.com/2026/07/researcher-drops-new-windows-zero-day.html)
- **トピック**: [Windows LegacyHive 特権昇格ゼロデイ（2026年7月）](../topics/windows-legacyhive-zero-day-2026.md)
- **分類**: 新規

## 概要

「Nightmare Eclipse」を名乗る研究者が、2026年7月Patch Tuesday公開の数時間後に、Windows User Profile Service（ProfSvc）の脆弱性を悪用する特権昇格ゼロデイ「LegacyHive」の一部実証コードを公開した。標準ユーザー権限であっても管理者を含む他ユーザーのレジストリハイブを自身のクラスルートにマウントできる不備で、完全にパッチ適用済みのWindows 10・11・Serverにも影響する。CVE番号は未付与。

## 詳細

### 脆弱性の技術的詳細

LegacyHiveは、Windows User Profile Service（ProfSvc）における任意のレジストリハイブ読み込みの不備を悪用する。サインイン時にユーザー設定をロードするこのコンポーネントの挙動を利用し、タイミングを合わせたパス切り替え（path-switching）のトリックによって、標準ユーザーが管理者を含む他ユーザーのレジストリハイブを自身のクラスルートにマウントできてしまう。これにより特権昇格や不正なクロスユーザーデータアクセスが可能になる。

### 影響範囲

Windows 10・Windows 11、および Windows Server（2016・2019・2022）を含む、サポートされているすべてのバージョンに影響する。2026年7月Patch Tuesdayで最新パッチを適用済みの環境でも影響を受ける、いわゆるゼロデイ状態にある。

### 公開の経緯

研究者「Nightmare Eclipse」は、Microsoftの元エンジニアではないかとも推測される人物で、過去にも6件のWindowsゼロデイを公開しており、そのうち3件はパッチ提供前に攻撃者に武器化された実績がある。今回のLegacyHiveは、広範な悪用を防ぐ目的から実証コード（PoC）が意図的に簡略化されており、完全に動作するPoCやCVE識別子は付与されていない。

### リスクと対応

現時点でMicrosoftからの正式パッチは提供されていない。特権昇格の脆弱性は単体では致命的でないことが多いが、初期侵入（フィッシングやリモートRCE等）と組み合わせることでランサムウェア攻撃者やAPTにとって強力な足がかりとなる。Microsoftからの公式パッチ提供まで、監査ログの強化や異常なレジストリハイブロード操作の監視が推奨される。

---

## 関連記事

なし（新規トピック）
