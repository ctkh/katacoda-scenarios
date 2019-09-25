K8sクラスタの準備は、Katacodaに任せました。

`kubectl cluster-info`{{execute}}

クラスタの状態を確認するコマンドです。以下のメッセージが出ることを確認してください。

※少し時間がかかることがあります

`Kubernetes master is running at ...`

K8sクラスタの構成を確認します。

`kubectl get nodes`{{execute}}

クラスタを構成するサーバの情報が出力されます。今回は、master　1台で試します。masterが、nodeを兼ねていると思ってください。

※複数サーバ構成を作るのに、それなりに時間がかかってしまうので...

STATUSが、`Ready`になるまでお待ちください。

今回は、K8sが提供してくれているサンプルアプリである、guestbookを利用してみます。

これを使った解説記事やブログはWebに多数載っているので、自己学習にもつながると思います。

サンプルアプリをGithubよりダウンロードします。

`git clone https://github.com/kubernetes/examples.git`{{execute}}