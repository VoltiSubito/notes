# Docker

  + List running containers `docker ps`
  + List all containers `docker ps -a`
  + List all images `docker images`
  + Remove a container `docker rm <CONTAINER_ID>`
  + Remove an image `docker rmi <IMAGE_ID>`
  + Forcibly remove an image `docker rmi -f <IMAGE_ID>`
  + Remove all images `docker images -q | xargs docker rmi`
  + Remove all containers `docker ps -a -q | xargs docker rm`
