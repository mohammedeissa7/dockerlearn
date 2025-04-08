# File Persistence via Commit
```

docker run -it --name ubuntu1 ubuntu touch /testfile

docker commit ubuntu1 ubuntu-with-file


docker rm ubuntu1

docker run -it --name ubuntu2 ubuntu-with-file ls /
```


# Volume Persistence Test

```
docker volume create myvol
docker run -it -v myvol:/data --name vol-test ubuntu bash

touch /data/volfile
exit

docker rm vol-test

docker run -it -v myvol:/data --name vol-test2 ubuntu ls /data
```

# Bridge Network Communication
```

docker network create mybridge

docker run -d --net mybridge --name c1 ubuntu sleep infinity
docker run -d --net mybridge --name c2 ubuntu sleep infinity

docker exec c1 ping c2
docker exec c2 ping c1
```
    
