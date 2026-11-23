# Rackspace Spot 不正アクセス・Kubernetes Secret露出（2026年11月）

## 概要

マネージドKubernetes基盤Rackspace Spotに対する、漏えい認証情報を用いた不正アクセス（2026年11月17日 00:20〜22:00 UTC頃）。顧客クラスタでのPod作成、Secret読み取り、ノード／ボリューム一覧取得が可能だった。管理コンソールが長時間停止し11月21日に全面復旧。IoC: 23.224.79.106、23.224.0.0/15、Pod名接頭辞 i1／glm-／probe。影響組織数と認証情報の出所は非公表。

## タイムライン

- [2026-11-23 Rackspace Spotに漏えい認証情報で不正アクセス、顧客KubernetesクラスタのSecret読み取りと不正Pod作成が可能な状態に](../articles/2026-11-23-rackspace-spot-breach-kubernetes-secrets.md)
