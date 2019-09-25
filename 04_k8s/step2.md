以下のマニュフェストファイルを見てみましょう。

`examples/guestbook/frontend-deployment.yaml`
`examples/guestbook/frontend-service.yaml`
`examples/guestbook/redis-master-deployment.yaml`
`examples/guestbook/redis-master-service.yaml`
`examples/guestbook/redis-slave-deployment.yaml`
`examples/guestbook/redis-slave-service.yaml`

※内容については、スライドで補足します

`examples/guestbook/frontend-service.yaml`だけ、編集します。

`- port: 80`の下に`NodePort: 10080`を追記してください。

### マニュフェストファイルの適用

以下のコマンドで、フォルダ配下のマニュフェストファイル(YAML)を適用しましょう。

`kubectl apply -f examples/guestbook/`{{execute}}

`-f`は、ファイル(ディレクトリ))を利用

DeploymentによってReplicaSet経由でreplicas分のPodと、Serviceが立ち上がったはずです。

`kubectl get pods`

`kubectl get rs`

`kubectl get svc`

それぞれ、`Pod`、`ReplicaSet`、`Service`を確認するコマンドです。