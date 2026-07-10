---
tags: [ソース, 概念, JVM, パフォーマンス]
source: raw/ガーベージコレクションとは.md
updated: 2026-07-07
---

# ソース要約: ガーベージコレクションとは

## 概要

インフラ運用の文脈で、ガーベージコレクション（GC）が何をする仕組みか、なぜ性能劣化や障害の兆候として監視対象になるかを説明したドキュメント。

## 主要なポイント

### GC の役割

- GC は JVM が不要メモリを自動回収する仕組み
- OpenSearch / Elasticsearch / Solr のような JVM ベースのミドルウェアで重要
- GC 自体は正常動作に必要であり、存在そのものが問題ではない

### インフラで重要になる理由

- GC が頻繁または長時間になると、処理停止や遅延（Stop The World）が発生し得る
- その結果として、レスポンス遅延、タイムアウト、5xx 増加につながることがある

### 監視で見るべき指標

- JVM Memory Pressure
- GC 回数
- GC 時間
- CPU 使用率
- Search latency
- 5xx / timeout

### 良くない状態の例

- JVM Memory Pressure が高止まり（例: 80% 超）
- GC が高頻度かつ長時間
- Search latency 上昇、queue 蓄積、5xx 増加

### 想定される原因

- JVM Heap 不足
- 重い検索クエリや aggregation
- fielddata / cache の過剰利用
- shard 数過多
- ノード不足
- bulk indexing 負荷
- メモリリークに近い状態

## 関連ページ

- [[ガーベージコレクション]]
- [[Latency]]
- [[Throughput]]
