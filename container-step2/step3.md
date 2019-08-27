index.htmlを差し替える必要が出てきました。編集しましょう。

※画面上のファイルエディタ、もしくはviコマンドなどで編集してみましょう。

編集後、改めてイメージをビルドしてみます。「設計図」は変わらないので、同じDockerfileが使えます。

`docker build -t mynginx .`{{execute}}

先ほどの出力イメージと比較してみると、ベースのnginxイメージ取得部分が早く終わっていると思います。

`docker image ls`{{execute}}
