```markdown
## Getting Started

### Check Docker Version
To check the installed version of Docker, run:
```bash
docker version
```

### Start Docker Daemon
Start the Docker daemon:
```bash
sudo systemctl start docker
```

### Check Docker Daemon Status
Check the status of the Docker daemon:
```bash
sudo systemctl status docker
```

## Managing Containers

### List All Containers
To list all containers, including inactive ones:
```bash
sudo docker container ls -a
```

### Remove a Container
Remove a specific container by its name or ID. Add `-f` to force removal:
```bash
docker container rm <container name or ID>
docker container rm -f <container name or ID>
```

### Expose Nginx on Port 8080
To run an Nginx container and expose it on port 8080:
```bash
sudo docker run --publish 8080:80 --detach nginx
```

## Container Logs and Monitoring

### Check Container Logs
To view the logs of a specific container, replace `<image name/id>` with the actual image name or ID:
```bash
sudo docker container logs <image name/id>
```

### Docker Monitoring Commands
Monitor the processes running in a specific container:
```bash
docker top <container name/ID>
docker logs <container name/ID>
docker stats <container name/ID>
```

### Detailed Container Information
Get detailed information about a specific container:
```bash
docker inspect <container name/ID>
```

## Executing Commands in Containers

### SSH Into a Running Container
Run and SSH into a container with an open STDIN, even if not attached:
```bash
docker run -it <image name/image id> <command>
```

### Enter a Running Nginx Container
To enter a running Nginx container:
```bash
docker container run -p 8080:80 -it --name nginx nginx /bin/bash
```

### Find a File Within the Container
Example to find `index.html` in the container:
```bash
find / -name "index.html"
cat /usr/share/nginx/html/index.html
```

### Exit From Container
To exit out from the container:
```bash
exit
```

### Execute Commands in an Existing Container
Execute commands in an existing container. For example, creating a file or opening a bash session:
```bash
docker exec -it <container name/id> touch /tmp/Docker
docker exec -it <container name/id> /bin/bash
```

### Interacting With MySQL Container
To interact with a MySQL container:
```bash
docker exec -it custom-mysql mysql -uroot -p
```

## Environment Variables

### Run Container With Environment Variables
Run a container with environment variables, such as setting the MySQL root password:
```bash
docker run --name my-sql -e MYSQL_ROOT_PASSWORD=123456 -d mysql
```
