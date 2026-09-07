# MikroTik RouterOS「MikroTrick」攻撃チェーン、SSH経由の未認証RCEが実悪用中

- **日付**: 2026-09-06
- **出典**: [CERT Polska](https://cert.pl/en/posts/2026/09/vulnerabilities-in-mikrotik-routeros-actively-exploited/), [MikroTik](https://mikrotik.com/supportsec/september-2026-vulnerability/)
- **トピック**: [MikroTik RouterOS「MikroTrick」SSH認証バイパス連鎖脆弱性（2026年9月）](../topics/mikrotik-routeros-mikrotrick-2026.md)
- **分類**: 新規

## 概要

CERT Polskaは2026年9月、MikroTik RouterOSに存在する複数の脆弱性を報告した。うちCVE-2026-67276とCVE-2026-86060を連鎖させる「MikroTrick」と呼ばれる攻撃チェーンにより、SSHサービスがインターネットに公開された機器を未認証のまま完全に乗っ取ることが可能で、実際にインターネット上で悪用が観測されている。

## 詳細

CVE-2026-67276は、RouterOSがSSH認証時にクライアント提示のRSA公開鍵と登録済み許可鍵を比較する際、鍵種別と法（modulus）のみを検証し指数（exponent）を検証しないという実装上の不備である。この結果、攻撃者は許可されたRSA鍵の法を知っていれば、指数を1に設定した鍵を用いて偽の署名を生成し、秘密鍵を保持しないまま対象ユーザーとしてSSHコマンドチャネルを開くことができる。

CVE-2026-86060は、SSHログイン処理において禁止文字で始まるユーザー名の引数処理に不備があり、これを悪用することでRouterOSの信頼ポリシーマスクを書き換え、権限昇格を引き起こすことができる。CERT Polskaによれば、この2件を組み合わせることでSSHサービスが外部公開されたRouterOS機器に対し、認証なしで管理者権限を完全に奪取できるといい、実際に外部からアクセス可能なRouterOS機器への攻撃が近日中に観測されているとしている。

CERT Polskaは他にもCVE-2026-67277（btestサービスにおけるカーネルメモリ開示およびDoS）を含む計6件の脆弱性（CVE-2026-67276〜67279、67281、86060）を報告している。MikroTikはRouterOS 7.25 beta3、7.24.2、7.23.4、6.49.21で修正版を公開済みで、通常構成では大きなリスクはないとしつつも、SSHサービスを外部公開している利用者には至急のアップデートを強く推奨している。RouterOSは家庭用から企業・ISP向けまで広範に採用されているルーターOSであり、影響を受ける機器の規模は大きいとみられる。
