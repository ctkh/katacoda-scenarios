コンテナの"中"に入ってみます。

と、その前に、ホスト上でテストファイルを作成しておきます。

`touch /tmp/testfile`{{execute}}

`ls -l /tmp/testfile`{{execute}}


では、コンテナを起動するコマンドを発行します。

`docker run -it ubuntu /bin/bash`{{execute}}

`-it`オプションで、コンテナの標準入出力にターミナルで繋いで操作できます。
(コンテナの中に入っているイメージ)

`ubuntu`の部分はイメージ名。`/bin/bash`は、コンテナで実行するコマンド。

<pre>
root@XXXXXXXXXXXX:/#
</pre>

実行すると、上記のようにプロンプトが変わると思います。(コンテナの中に入りました)

ホスト上で作ったファイルは、コンテナから見えるでしょうか？

`ls -l /tmp/testfile`{{execute}}

ホストに戻りましょう。

`exit`{{execute}}

