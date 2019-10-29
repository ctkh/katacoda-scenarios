### Podの起動

`green`のPodを起動します。

`kubectl apply -f node-deployment-green.yaml`{{execute}}

それぞれのリソースを確認してみましょう。(blueもgreenもできているはず)

`kubectl get pods`{{execute}}

`kubectl get rs`{{execute}}

`kubectl get deployment`{{execute}}

### Serviceの起動

Serviceについては、外部に公開するポートはそのまま、振り分け先を`green`に切り替えたいです。

よってService名(`metadata.name`)は据え置き、振り分け条件を変えます。先ほどPodに振った、`color: green`のラベルを条件にしましょう。

`cat nginx-service-green.yaml`{{execute}}

それでは適用...の前に、`blue`の画面を脇に出しながらやってみましょう。

`kubectl apply -f nginx-service-green.yaml`{{execute}}

`kubectl get svc`{{execute}}

バツっと切り替わっ...てほしいのですが、たまに`blue`が混じります。しばらくたつと、`green`に寄ります。(感覚的には5分くらい)

調べると同じようなことが書いているものが結構ありました。パラメータの調整等が必要そうですが、今日は深堀できません。

きれいに切り替わったテイで、`blue`を落としてしまいましょう。

`kubectl delete -f node-deployment.yaml`{{execute}}

`kubectl get pods`{{execute}}

### まとめ

いわゆるBlue/Green Deploymentっぽいものを試してみました。

もちろんK8sでなくてLB機器や複数台のサーバを利用することでも同じようなことは可能ですが、コードや設定ファイルを書く感覚でやれてしまうのが、K8sならではのところでしょうか。(Infrastructure as a code)