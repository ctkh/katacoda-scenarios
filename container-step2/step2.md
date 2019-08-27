イメージを作成します。カレントディレクトリのDockerfileに従います。

`docker build -t mynginx .`{{execute}}

※この時の画面出力、覚えておいてください。

イメージを確認してみましょう。

`docker image ls`{{execute}}

作ったイメージを利用して、コンテナを起動してみます。

`docker run  -d  -p 10080:80  --name myweb mynginx`{{execute}}

ブラウザで見てみてください。あなたのindex.htmlが見えましたでしょうか。
