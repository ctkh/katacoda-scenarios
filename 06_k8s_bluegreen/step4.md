### Podの起動

PodがマウントするConfigMapの作成が無事に終わりました。それでは、Podを起動していきましょう。

Podは、Deploymentを適用することにより、Deployment→ReplicaSet→Podと起動しますね。

`kubectl apply -f node-deployment.yaml`{{execute}}

それぞれのリソースを確認してみましょう。

`kubectl get pods`{{execute}}
`kubectl get rs`{{execute}}
`kubectl get deployment`{{execute}}

### Serviceの起動

Podを起動しただけでは、K8sクラスタの外部からの接続はできません。Podを束ねて外部に公開する機能、Serviceを起動します。

`kubectl apply -f nginx-service.yaml`{{execute}}

`kubectl get svc`{{execute}}

上手くいけば、`:30080`で受信したアクセスを、`:80`へ振り分けるServiceができているはずです。

Katacodaのブラウザで確認してみましょう。

### まとめ

ConfigMapを利用して、設定ファイルやHTMLをコンテナの外に切り出しました。これにより、左記のファイルが変更された際も、コンテナイメージのビルドは不要となります。

なお変更時は、新しいConfigMapを作成し、それをマウントするDeploymentを作成し、Podを起動しなおすことになります。

この時の影響を極力抑えるデプロイ方法(Blue-Green Deployment)を、次のシナリオで見てみます。

