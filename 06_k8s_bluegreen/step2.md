## 各種リソースの起動

先ほどのリソースが起動していた状態まで、一気に進めてしまいます。

`kubectl create configmap --save-config cm-nginx-conf --from-file=./nginx.conf `{{execute}}

`kubectl create configmap --save-config cm-nginx-html-blue --from-file=./blue.html`{{execute}}

`kubectl apply -f node-deployment.yaml`{{execute}}

`kubectl apply -f nginx-service.yaml`{{execute}}

`30080`で接続できるか、確認しましょう。


## 改修

「背景色を緑に変えたい」という要望がありました。画面はConfigMapにしておいたので、その修正でよさそうです。

マウントするConfigMapを変える必要があるので、Deployは変えることになります。

また、デプロイする際には極力ダウンタイムを小さく、すぐ切り戻せるような方法をとる必要があります。

⇒ Blue/Green Deployment(B/G)