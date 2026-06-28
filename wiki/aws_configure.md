---
tags: [概念, AWS, CLI]
sources: [aws_configureとは.md]
updated: 2026-06-28
---

# aws configure（AWS CLIプロファイル）

## 概要

`aws configure` は AWS CLI の認証情報・接続設定をローカルに保存するコマンド。`--profile` オプションを使うことで、複数の設定セット（プロファイル）を名前付きで管理できる。

## デフォルト vs 名前付きプロファイル

| コマンド | 保存先 |
|---|---|
| `aws configure` | `[default]` プロファイル |
| `aws configure --profile dev` | `[dev]` プロファイル |

## 設定項目

```
AWS Access Key ID
AWS Secret Access Key
Default region name   (例: ap-northeast-1)
Default output format (例: json)
```

## プロファイルの切り替え方法

```bash
# コマンド単位で指定
aws s3 ls --profile dev

# 環境変数で一時的に指定（シェルセッション全体に適用）
export AWS_PROFILE=dev
aws s3 ls
```

## 設定ファイルの保存先

```
~/.aws/credentials   # Access Key ID / Secret Access Key
~/.aws/config        # リージョン・出力フォーマット等
```

## ユースケース

- 開発環境と本番環境でアカウントを分離する
- 複数のAWSアカウントを1台のマシンから操作する
- CI/CD環境では環境変数 `AWS_PROFILE` や `AWS_ACCESS_KEY_ID` で切り替える

## 関連ページ

- [[source_aws_configureとは]] — ソース要約
