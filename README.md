A minimal lightweight  mysql docker image based on alpine with mysql (~ about 179 MB)

# How to build image

`git clone ..` , then:

```
docker build -t batlley/alpine-mysql .
```

# How to start a container

To start the server without creating an initial user/database:

```
docker run -it --rm --name mysql -v $(pwd):/data -p 3306:3306 batlley/alpine-mysql
```

OR

To start the server and create an initial user (e.g john/doe), database (e.g my_db) and specify root password (root\_pass):

```
docker run -it -rm --name mysql -p 3306:3306 -v $(pwd):/data -e MYSQL_DATABASE=my_db -e MYSQL_USER=john -e MYSQL_PASSWORD=doe -e MYSQL_ROOT_PASSWORD=root_pass batlley/alpine-mysql
```

#How to manage mysql (mysql cli)

Once the container is running, run:

```
docker exec -it mysql sh
```

to connect, then type:  `` mysql -uroot -p``


