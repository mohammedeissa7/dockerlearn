# Custom Apache Image

1. Run httpd without volumes : 

```
docker run -d --name temp-apache -p 8080:80 httpd
```

2. Add HTML files to the container : 

```

echo "<h1>My Custom Apache Page</h1>" > index.html

docker cp index.html temp-apache:/usr/local/apache2/htdocs/
```

3. Commit the container as a new image : 

```
docker commit temp-apache my-custom-apache
docker images
```

4. build the image : 

```
docker build -t my-custom-apache-dockerfile .
```
5. Run and test new image : 

```
docker run -d --name custom-apache -p 8081:80 my-custom-apache-dockerfile
```
