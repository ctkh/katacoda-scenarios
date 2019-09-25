Dockerfileでは、`FROM`、`COPY`以外でも様々なコマンドが使えます。

代表的なコマンドを利用しながら、より実践的なDockerfileを作ってみようと思います。

なお、コマンドの詳細は公式ページなども参照してください。

http://docs.docker.jp/engine/reference/builder.html

コマンドについては、サンプルのDockerfile内のコメントで説明します。まずは見てみましょう。

なお以下のようなシチュエーションにいると想定してください。

- 公式のnginxイメージはDebianベースであるが、諸事情あってCentOSベースにしたい。
  そこでCentOSイメージをベースに、自分でnginxのインストールから実行する。

`cd container-lesson/day1/nginx2`{{execute}}

`cat Dockerfile`{{execute}}

※上のエディタで見ると、日本語が化けます。。catの結果をコピーして、テキストエディタ等にコピーしてご覧ください。