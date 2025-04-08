# Interactive Docker Container 

1. Run container in interactive mode : `docker run -it --name my-ubuntu ubuntu /bin/bash`

2. Create a file named hello-docker : 

```
touch hello-docker
ls  # Verify the file was created
exit  # Exit the container
```

3. Stop and remove the container : 

```
docker stop my-ubuntu
docker rm my-ubuntu
```

4. Remove all stopped containers : `docker container prune`