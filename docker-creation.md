#these commands will help you create your docker image and container. they can assist with other tasks as well.
cd wedding-main/

ls

cat Dockerfile

docker build -t wedding-image .

docker images

#after running this command you should be able to use the EC2 public ip address with port 80 and see the application
docker run -d -p 80:80 wedding-image

docker ps

#for troubleshooting
docker exec -it <container-id> /bin/bash

#to look at logs
docker logs <container-id>

#stop container
docker stop <container-id>

#see all containers including stopped ones
docker ps -a

#delete container
docker rm <container-id>
