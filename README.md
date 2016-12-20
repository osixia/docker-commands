docker-commands on ubuntu
===============

### Stop all containers

    sudo docker stop $(sudo docker ps -a -q)

### Remove all containers

    sudo docker rm $(sudo docker ps -a -q)

### Remove all exited containers

    sudo docker ps -a | grep Exit | cut -d ' ' -f 1 | xargs sudo docker rm

### Remove orphaned volumes
    
    docker volume rm $(docker volume ls -qf dangling=true)

### Remove all images

    for i in `sudo docker images|awk '{print $3}'`;do sudo docker rmi $i;done

### Pull again all images
    
    docker images --filter "dangling=false" --format "{{.Repository}}:{{.Tag}}" | xargs -L1 docker pull
