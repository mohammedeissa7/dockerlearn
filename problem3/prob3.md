# Apache HTTPD Container with Volumes

1. Create volumes and run initial container : 
```

docker volume create apache-html
docker volume create apache-config


docker run -d  --name apache -v apache-html:/usr/local/apache2/htdocs -v apache-config:/usr/local/apache2/conf httpd
```
2. Remove the initial container : 

```
docker stop apache
docker rm apache
```

3. Run new container with volume mounts and port mapping : 

```
docker run -d --name new-apache -v apache-html:/usr/local/apache2/htdocs -v apache-config:/usr/local/apache2/conf -p 9898:80 httpd
```

4. Access HTML files from browser : 

```
docker volume inspect apache-html


docker exec new-apache sh -c "echo '<h1>Hello Docker Apache!</h1>' > /usr/local/apache2/htdocs/index.html"
```