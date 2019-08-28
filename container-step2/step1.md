あらかじめサンプルを用意しました。ダウンロード先のディレクトリに移動します。
※失敗する場合は、何回か試してください。

`cd ./container-lesson/day1/nginx`{{execute}}

コンテナイメージの設計図、Dockerfileを見てみます。

`cat Dockerfile`{{execute}}

`FROM nginx:1.17`は、nginxイメージをベースにするという宣言です。`:1.17`の部分はタグと呼ばれますが、バージョンのニュアンスで使われます。

タグを省略した場合、もしくは`:latest`とした場合、その時点の最新版を利用します。商用用途では、基本的にはバージョンを明に指定することになると思います。

`COPY index.html /usr/share/nginx/html`は、カレントディレクトリの`index.html`を、イメージ内の`/usr/share/nginx/html`にコピーしています。

`index.html`のサンプルファイルです。事前に確認してみましょう。

`cat index.html`{{execute}}