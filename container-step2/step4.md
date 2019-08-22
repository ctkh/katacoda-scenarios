`docker build -t mynode .`{{execute}}

`docker run -d -p 10081:80 --name myweb2 mynode`{{execute}}
