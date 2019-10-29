### ConfigMapの作成

- nginx.conf の作成

`kubectl create configmap --save-config cm-nginx-conf --from-file=./nginx.conf `{{execute}}

カレントディレクトリの`nginx.conf`をもとに、`cm-nginx-conf `という名のConfigMapを作成しています。

この時、Key=ファイル名(nginx.conf)、Value=<ファイルの中身>というjsonが作成されます。

`kubectl get configmaps cm-nginx-conf -o json | jq`{{execute}}

- htmlを持つConfigMap の作成

スライドで触れたとおり、ConfigMapの中身がコンフィグかどうかはあまり関係なく、Key＆Value形式で定義したものをファイルとしてPodにマウントできます。  
これを活用して、htmlもConfigMapに乗せてしまいましょう。

`kubectl create configmap --save-config cm-nginx-html-blue --from-file=./blue.html`{{execute}}

`kubectl get configmaps cm-nginx-html-blue -o json | jq`{{execute}}