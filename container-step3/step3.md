まずは、ディレクトリを移動します。

`cd ../node`{{execute}}

以下のイメージを作成する、Dockerfileを作成し、イメージをビルドし、コンテナを起動してみましょう！

なおDockerfileはvi等で書いてもいいですし、1回touchして作成したあと、上のエディタで書いてもいいです。

`touch Dockerfile`{{execute}}

- `node:10`(Node.js)をベースイメージとします
- `node`では、任意のディレクトリでアプリを動かせます。関連ファイルは全部どこかにまとめておいてしまいましょう。
- アプリを起動するのに必要なパッケージが記載してある`package.json`を、カレントディレクトリに置いてます。
- `package.json`があるディレクトリで、`npm install`というコマンドを打つと、必要なパッケージをダウンロードします。(npm=nodeのパッケージ管理ツール)
-  サンプルアプリ`app.js`も、カレントディレクトリに置いてます。
- `node app.js`というコマンドで、app.jsを起動できます。
- `app.js`は、`12345`ポートをListenし、文言を返却するアプリです。

Dockerfileの作成が終わったら、ビルド＆コンテナ起動をしてみましょう。(イメージ名、コンテナ名は任意です)

`docker build -t mynode:1.0 .`{{execute}}

`docker run  -d  -p 12345:12345 --name nodex mynode:1.0`{{execute}}

ブラウザで、以下の文言が出てくれば成功です。

`Hello from Node.js Container, Let's enjoy studying!`

正解のサンプルを置いてますので、困ったらどうぞ。

`cat Dockerfile.sample`{{execute}}

上手くいきましたでしょうか？

アプリの入った小さなサーバ(＝コンテナ)が、1つのテキストファイル(Dockerfile)で簡単に作れる　というのを体感できたでしょうか。

以上で、本シナリオは終了します。