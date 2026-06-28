aws configure --profile とは
思考時間: 4s

aws configure --profile は、AWS CLI の設定を「名前付き」で保存するコマンドです。

通常の設定はこれです。

aws configure

これはデフォルト設定として保存されます。

一方で、

aws configure --profile dev

とすると、dev という名前の設定を作れます。

入力する内容はだいたいこれです。

AWS Access Key ID [None]: xxxxx
AWS Secret Access Key [None]: xxxxx
Default region name [None]: ap-northeast-1
Default output format [None]: json

例えば開発用・本番用で分けたいときに便利です。

aws configure --profile dev
aws configure --profile prod

使うときはこうです。

aws s3 ls --profile dev

または一時的に環境変数で指定できます。

export AWS_PROFILE=dev
aws s3 ls

設定は主にこの2つのファイルに保存されます。

~/.aws/credentials
~/.aws/config

イメージとしては、

profile = AWS接続設定の名前

です。

なので aws configure --profile test は、
「test という名前でAWS認証情報を保存する」 という意味です。