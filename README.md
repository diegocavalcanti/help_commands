#Linux Commands

##corrigir caracteres inválidos do windows para funcionar no linux
sed -i -e 's/\r$//' script-deploy-prod.sh


#Docker Commands

##List all Docker Images
docker images -q

##Removing Docker Image or images

// to remove one specific image
docker rm image1

// to remove two (more) specific images, just mention list
docker rm image1 image2

##Removing All Docker Image
docker rmi $(docker images -q)

##Remove a container(s)
// to remove one specific container
docker rm container1
// to remove two (more) specific container, just mention list
docker rm container1 container2

#3Remove a container and its volume
docker rm -v container_name

##List all containers (only IDs)
docker ps -aq

##Stop all running containers
docker stop $(docker ps -aq)

##Remove all containers
docker rm $(docker ps -aq)

#Remove all exited containers
docker rm $(docker ps -a -f status=exited -q)

##Remove containers using more than one filter
docker rm $(docker ps -a -f status=exited -f status=created -q)

##clean all in one command
docker system prune

##Docker IP
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container-id

