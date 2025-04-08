# MySQL Database with Docker
1. Create the persistent volume:
```
docker volume create mysql_data
```
2. Deploy MySQL container with the volume :

```
docker run -d --name app-database -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=P4sSw0rd01 mysql:latest

```
3. Check volume was created properly :

```
docker volume inspect mysql_data
```

4. Connect to MySQL to verify:

```
docker exec -it app-database mysql -uroot -pP4sSw0rd01
```