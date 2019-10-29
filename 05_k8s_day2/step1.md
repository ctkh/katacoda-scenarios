クラスタの状態を確認するコマンドです。

`kubectl cluster-info`{{execute}}

以下のメッセージが出ることを確認してください。少し時間がかかることがあります。

`Kubernetes master is running at ...`

K8sクラスタの構成を確認します。

`kubectl get nodes`{{execute}}

前回同様、master　1台で試します。(node兼任)

STATUSが、`Ready`になるまでお待ちください。

今回は、nginxを利用した自作のサンプルで試します。Githubよりダウンロードし、移動しておきます。

`git clone https://github.com/ctkh/k8s-lesson.git`{{execute}}

`cd k8s-lesson`{{execute}}