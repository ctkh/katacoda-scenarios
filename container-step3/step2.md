イメージをビルドしてみましょう。

`docker build -t mynginx2:1.0 .`{{execute}}

Dockerfileに書いたコマンドが`Step`として表示されると思います。出力イメージを追ってみてください。

成功したら、コンテナを起動してみます。

`docker run  -d  -p 20080:80 --name web10 mynginx2:1.0`{{execute}}

`index.html`が表示されたでしょうか。

次は、自分でDockerfileを作ってみましょう。