`docker build -t mynginx .`{{execute}}

`docker run  -d  -p 10080:80  --name myweb mynginx`{{execute}}
