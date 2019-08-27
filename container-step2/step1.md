あらかじめサンプルを用意しました。ダウンロード先のディレクトリに移動します。
※失敗する場合は、何回か試してください。

`cd ./container-lesson/day1/nginx`{{execute}}

コンテナイメージの設計図、Dockerfileを見てみます。

`cat Dockerfile`{{execute}}

`FROM nginx`は、nginxイメージをベースにするという宣言です。

`COPY index.html /usr/share/nginx/html`は、カレントディレクトリの`index.html`を、イメージ内の`/usr/share/nginx/html`にコピーしています。

`index.html`のサンプルファイルです。好きなように書き換えていただいて構いません。

`cat index.html`{{execute}}