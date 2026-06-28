---
tags: [ソースページ, AWS, CLI]
sources: [aws_configureとは.md]
updated: 2026-06-28
---

# source: aws_configureとは.md

## 概要

`aws configure --profile` は、AWS CLI の認証情報・設定を「名前付き」で保存するコマンド。複数のAWS環境（開発・本番など）を切り替えるために利用する。

## 主なポイント

- `aws configure` — デフォルト設定として保存
- `aws configure --profile <名前>` — 名前付きプロファイルとして保存
- 設定項目: Access Key ID、Secret Access Key、デフォルトリージョン、出力フォーマット

## プロファイルの使い方

```bash
# コマンド単位で指定
aws s3 ls --profile dev

# 環境変数で一時的に指定
export AWS_PROFILE=dev
aws s3 ls
```

## 設定ファイルの保存先

| ファイル | 内容 |
|---|---|
| `~/.aws/credentials` | Access Key ID・Secret Access Key |
| `~/.aws/config` | リージョン・出力フォーマット等 |

## 関連ページ

- [[aws_configure]] — AWS CLI プロファイル機能の詳細
