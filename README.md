# Task4
1.  Create a new bridged network `my_network` with following command:
```console
$ docker network create my_network
```
2.  Attach the network `my_network` with existing image `nginx`by using follwoing command:
 ```console
$ docker run -itd --name nginx_container --network=my_network nginx
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS         PORTS     NAMES
c486b9ca0a7f   nginx     "/docker-entrypoint.…"   11 seconds ago   Up 8 seconds   80/tcp    nginx_container
```
3.  To see the running container with `my_network` run following command:
```console
$ docker ps --filter network=my_network
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS     NAMES
c486b9ca0a7f   nginx     "/docker-entrypoint.…"   22 minutes ago   Up 22 minutes   80/tcp    nginx_container
```
4. the container is accessable on `localhost:8080`
![image](https://user-images.githubusercontent.com/126319802/228525590-da2e00ae-57b9-41d2-a053-4c42ec5cc172.png)
5. stop and remove `nginx_container` with following comamnds:
```console
$ docker stop nginx_container
$ docker rm nginx_container
```
6. 
