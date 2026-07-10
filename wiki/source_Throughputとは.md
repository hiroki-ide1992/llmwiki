---
tags: [ソース, パフォーマンス, インフラ]
sources: [Throughputとは.md]
updated: 2026-07-01
---

# source: Throughputとは.md

## 概要

スループット（Throughput）とは「一定時間あたりに処理できる量」を表す性能指標。

## 主なポイント

- 道路の比喩: 1分間に何台の車が通れるか、に対応
- Web/API 文脈での代表的な観点:
  - RPS / req/s — 1秒あたりのリクエスト数
  - TPS — 1秒あたりのトランザクション数
  - MB/s・GB/s — 1秒あたりのデータ転送量
  - IOPS — 1秒あたりのI/O回数

## Throughput vs Latency

| 用語 | 意味 | 比喩 |
|------|------|------|
| Throughput | どれだけ大量に処理できるか | レジが1時間に何人さばけるか |
| Latency | 1件の処理にかかる時間 | 1人の会計が完了するまでの秒数 |

## インフラのボトルネック例

以下の状態になると Throughput が頭打ちになる:

- CPU 使用率が高い
- DB 接続数が不足
- ネットワーク帯域が不足
- OpenSearch の search queue が詰まる
- ECS タスク数が少ない
- ALB 配下のサーバーが処理しきれない

Throughput が頭打ちになると待ち行列が発生し、結果的に Latency も悪化する。

## 関連ページ

- [[Throughput]]
- [[Latency]]
