### ReplicaSetの確認

あたらめて、Podを見てみます。

`kubectl get pod`{{execute}}

一番最後の文字列は、起動したPodごとに異なるランダムな文字列です。皆さん異なります。

試しに、frontendのPodを1つ落としてしまいましょう。

`kubectl delete pod frontend-XXXXXXXXX-XXX`{{execute}}

※後ろの文字列はランダムなので、自分が確認したものに置き換えてください。

`kubectl get pod`{{execute}}

もう一度確認するとどうでしょうか。

### レプリカ数の変更

以下のファイルの、レプリカ数(replicas)を変更してみましょう。

`examples/guestbook/frontend-deployment.yaml`

変更したら、適用してみます。

`kubectl apply -f examples/guestbook/frontend-deployment.yaml`

`kubectl get pod`{{execute}}

レプリカ数が変わったでしょうか？

次回は、新しいアプリのバージョンアップなどを体験したいと思います。