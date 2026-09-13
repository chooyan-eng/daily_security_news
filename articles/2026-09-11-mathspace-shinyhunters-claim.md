# Mathspace侵害、ShinyHuntersが犯行声明 パッチ適用の遅れが被害拡大の一因に

- **日付**: 2026-09-11
- **出典**: [SecurityWeek](https://www.securityweek.com/mathspace-data-breach-exposes-over-1-million-people/), [Help Net Security](https://www.helpnetsecurity.com/2026/09/08/mathspace-data-breach-metabase-vulnerability/), [cybersecuritynews.com](https://cybersecuritynews.com/mathspace-data-breach/)
- **トピック**: [Metabase SQLインジェクションゼロデイ（CVSS 10.0、2026年8月）](../topics/metabase-sqli-zeroday-2026.md)
- **分類**: 続報

## 概要

豪教育アプリMathspaceの自己ホスト型Metabase侵害（CVE-2026-72898、108万人分のデータ流出）について、恐喝グループShinyHuntersが犯行声明を出した。Mathspaceが8月6日のパッチ公開後もMetabase推奨の追加侵害確認を怠っていたため、既に発生していた侵入が9月3日まで発覚しなかったことも判明した。

## 詳細

Mathspaceの自己ホスト型Metabaseインスタンスに対する不正アクセスは2026年8月10日に開始され、8月27日にはオーストラリアのレポーティングデータベースからデータがダウンロードされていたことが内部調査で確認されている。悪用された脆弱性はMetabaseのパスワードリセットエンドポイント（POST /api/session/reset_password）に存在する未認証SQLインジェクション（CVE-2026-72898、CVSS 10.0）で、既存のMetabase SQLiゼロデイ事案（Framework、Tally、n8n等）と同一のものである。

注目すべき点は、Mathspaceが脆弱性の正式パッチを8月29日に適用していたにもかかわらず、Metabaseが推奨していた「パッチ適用前の期間に侵害が発生していないかの追加確認作業」を実施していなかったことである。このため、パッチ適用前に既に発生していた不正アクセスの痕跡は見過ごされ、過去のアクセスログを遡った再調査を経て9月3日になってようやく侵害が確認された。

流出したデータは生徒・教員・保護者・スタッフの氏名、ユーザーID、ユーザー名、メールアドレス等のメタデータで、主にオーストラリア・ニュージーランドの利用者が対象。パスワードハッシュや認証トークン、SSO認証情報、成績・学習履歴などの学習記録は含まれていないとされる。影響を受けた人数は合計1,079,819人。

Metabaseのアドバイザリ公開直後、恐喝グループ「ShinyHunters」が本件の犯行声明を出した。ShinyHuntersは2026年後半に複数のSaaS・BIツールの脆弱性を悪用した大規模恐喝キャンペーンを展開しており、本件もその一環とみられる。Mathspaceは該当のレポーティングシステムをオフライン化し、学校・教育当局・サイバーセキュリティ機関への通知、および脆弱性対応後の侵害有無確認プロセスの見直しを進めているとしている。

---

## 関連記事

- [ShinyHunters SaaS恐喝キャンペーン（2026年8月）](../topics/shinyhunters-saas-extortion-campaign-2026-08.md) - 本件の犯行声明を出した恐喝グループの一連のキャンペーン
