# Google・Mandiant、Citrix NetScalerゼロデイの悪用でWHIPSHOT・SLAPSHOTウェブシェルによるroot権限奪取を報告

- **日付**: 2026-09-30
- **出典**: [Google Cloud Threat Intelligence（検索結果より）](https://cloud.google.com/blog/topics/threat-intelligence/citrix-zero-day-espionage/)
- **トピック**: [Citrix NetScaler ADC/Gateway CVE-2026-88771／CVE-2026-88772 RCEゼロデイ（2026年9月）](../topics/citrix-netscaler-cve-2026-88771-88772-zero-day.md)
- **分類**: 続報

## 概要

MandiantとGoogle Threat Intelligence Groupが、Citrix NetScalerの2件の重大ゼロデイの悪用を解説し、カスタムウェブシェル「WHIPSHOT」「SLAPSHOT」でroot権限を得る手口を報告したと伝えられた。

## 詳細

- 検索結果の要約では、攻撃者が2件の重大なNetScalerゼロデイを悪用してrootアクセスを得て、ステルス性の高いウェブシェル（WHIPSHOT、SLAPSHOT）を設置したとされる。既存トピックのCVE-2026-88771／88772に対応する可能性が高い。
- 注意: 引用元URLはGoogle Cloudの過去記事（2023年のCVE-2023-3519）と同じパスの形式で、今回の検索では新規報告の本文を直接確認できていない。CVE番号やIOCの詳細は未確認のため、Citrix公式アドバイザリと突き合わせること。
- 対処はパッチ適用に加え、侵害調査（ウェブシェル、不審な設定変更の確認）が必要。CISA KEVの期限は9月30日。

---

## 関連記事

