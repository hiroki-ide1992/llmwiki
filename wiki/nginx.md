---
tags: [エンティティ, ソフトウェア, ネットワーク]
sources: [raw/リバースプロキシとは.md]
updated: 2026-06-28
---

# nginx

高性能なオープンソースのWebサーバー兼[[リバースプロキシ]]。イゴール・シソエフにより開発。

## 主な機能

- Webサーバー（静的ファイル配信）
- リバースプロキシ
- ロードバランサー（[[負荷分散]]）
- SSL/TLS終端
- HTTPキャッシュ

## リバースプロキシとしての基本設定

```nginx
location /proxy/ {
    proxy_pass https://example.com/;
}
```

`http://localhost:8080/proxy/page` へのリクエストを `https://example.com/page` へ転送する。

## CORSとの関係

nginx をリバースプロキシとして使うことで、ブラウザから見たアクセス先を `localhost`（同一オリジン）にまとめられる。外部サイトへの実際の通信は nginx が担うため、[[CORS]] 制限を受けない。

## 関連ページ

- [[リバースプロキシ]]
- [[CORS]]
