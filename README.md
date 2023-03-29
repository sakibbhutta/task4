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
6. To Create a new Docker container using the `nginx` image and connecting it to the `my_network` network with container name `nginx_container_2`
run follwoing command:
```console
$ docker run -d --name nginx_container_2 --network=my_network nginx
```
![image](https://user-images.githubusercontent.com/126319802/228528341-54224980-ece0-4f08-8f74-49dadd512943.png)

7. Browse `localhost:8081` to see if nginx is running:
![image](https://user-images.githubusercontent.com/126319802/228528898-b6da0c07-22e6-4ae0-85f1-c891d596fb07.png)

8. Run following command to run `httpd_container` from `httpd` image:
```console
$ docker run -d --name httpd_container --network=my_network httpd
```
9.  Browse `localhost:8082` to see if httpd container is running:
10. run following command to list down the running containers:
```console
$ docker ps
```
![image](https://user-images.githubusercontent.com/126319802/228530009-e273d00a-b1d7-4706-bb01-51c054678b98.png)

11. Stop and remove all containers with following commands:
```console
$ docker stop httpd_container
$ docker stop nginx_container
$ dokcker stop nginx_container_2
$ docker container prune
```
12. Remove the `my_network` with following command:
```console
$ docker network rm my_network
```
