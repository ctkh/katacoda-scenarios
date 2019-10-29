クラスタの起動まで待ちます。

`kubectl cluster-info`{{execute}}

以下のメッセージが出ることを確認してください。少し時間がかかることがあります。

`Kubernetes master is running at ...`

K8sクラスタの構成を確認します。

`kubectl get nodes`{{execute}}

STATUSが、`Ready`になるまでお待ちください。

先ほどと同じサンプルを利用します。

`git clone https://github.com/ctkh/k8s-lesson.git`{{execute}}

`cd k8s-lesson`{{execute}}