### ConfigMapの作成

HTMLの入ったConfigMapを作成します。`green.html`をもとに、`cm-nginx-html-green`を作りましょう。

`kubectl create configmap --save-config cm-nginx-html-green --from-file=./green.html`{{execute}}

`kubectl get configmaps cm-nginx-html-green -o json | jq`{{execute}}

※`cm-nginx-conf`は設定変更しなくてよいとします。


### Deploymentの作成

`cm-nginx-html-green`をマウントする、Deploymentを作成します。

`cat node-deployment-green.yaml`{{execute}}

- ファイル名はあまり関係ありません。metadata.nameがDeployment名となります。  
  これが異なると、異なるDeploymentとみなされます。

- Podに`color: green`のラベルを付与しています。(後々活用します)

### デプロイの戦略

極力シームレスな切り替えのため、以下の戦略をとります。(いわゆるB/G)

- 既存(`blue`)は残したまま、`green`のDeployment>ReplicaSet>Podを起動しておく(まだアクセスはこない)

- Serviceを更新する。更新したタイミングから、`green`に切り替わるようにする。

- 切り替え後、もし異常が発生したら、すぐにServiceを戻し、`blue`に切り替えなおす。

- しばらく様子をみて正常に切り替わったら、`blue`のDeploymentを削除する。

