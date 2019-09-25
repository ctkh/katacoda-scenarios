ビルドした新しいイメージを利用して、コンテナを起動してみます。

`docker run  -d  -p 10081:80  --name myweb2 mynginx:1.1`{{execute}}

`docker ps`{{execute}}

今回もブラウザで見てみてください。画面が変わりましたでしょうか。

### 非コンテナ環境との違い

非コンテナ環境でミドルウェアのバージョンアップをするとなった場合、リリースはいいとして、切り戻しに悩むことが多いと思います。
(一度バージョンアップしたものが綺麗に戻せるのか、サーバ上の色んな所にモジュールが散らばって完全には戻せないのではないか、etc...)

コンテナ環境の場合は、コンテナイメージの中にミドルウェア(ランタイム)が含まれ、イメージのバージョンが違えば別物として管理されます。

よって`mynginx:1.1`でどのバージョンの`nginx`を使おうが、`mynginx:1.0`には何の影響もありません。切り戻したければ、`mynginx:1.0`を利用してコンテナを起動しなおすだけです。

また前段にLBを挟み、`10080(myweb1)`が開いた状態から`10081(myweb2)`を開け、`10080`を閉塞するという操作で、
シームレスなバージョンアップができます。

非コンテナの場合も、例えば2倍のサーバを構築すれば同じことができます。しかし、構築や管理の手間を考えると、コンテナの優位性を感じられのでは、と思います。

以上で、本シナリオは終了します。