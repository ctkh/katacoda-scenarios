イメージを作成します。カレントディレクトリのDockerfileに従います。

`docker build -t mynginx:1.0 .`{{execute}}

`-t <イメージ名>:<タグ名>`で名前とタグ(バージョン)を指定します。

※このビルドの時の画面出力、覚えておいてください。

イメージを確認してみましょう。

`docker image ls`{{execute}}

作ったイメージを利用して、コンテナを起動してみます。

`docker run  -d  -p 10080:80  --name myweb1 mynginx:1.0`{{execute}}

ブラウザで見てみてください。あなたのindex.htmlが見えましたでしょうか。
