# Windows LegacyHive 特権昇格ゼロデイ（2026年7月）

## 概要

研究者「Nightmare Eclipse」が2026年7月Patch Tuesday直後に公開した、Windows User Profile Service（ProfSvc）を悪用する特権昇格ゼロデイ「LegacyHive」。タイミングを合わせたパス切り替えにより、標準ユーザーが管理者を含む他ユーザーのレジストリハイブを自身のクラスルートにマウントできる。完全パッチ適用済みのWindows 10・11・Server（2016・2019・2022）にも影響。CVE番号・完全なPoCは未公開（広範な悪用防止のため簡略化）。

**同一性の判断に役立つ情報：**
- 脆弱性名: LegacyHive
- 公開者: 研究者「Nightmare Eclipse」
- 対象コンポーネント: Windows User Profile Service（ProfSvc）
- 脆弱性種別: 任意のレジストリハイブ読み込みによるローカル特権昇格
- 対象OS: Windows 10・11、Windows Server 2016・2019・2022（フルパッチ適用済みでも影響）
- CVE: 未付与
- 公開日: 2026年7月14日（2026年7月Patch Tuesday直後）

## タイムライン

- [2026-07-18 「LegacyHive」：Windows User Profile Serviceを悪用する特権昇格ゼロデイがPatch Tuesday直後に公開](../articles/2026-07-18-windows-legacyhive-zero-day.md)
