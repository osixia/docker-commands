docker-commands on ubuntu
===============

### Stop all containers

    sudo docker stop $(sudo docker ps -a -q)

### Remove all containers

    sudo docker rm $(sudo docker ps -a -q)

### remove all exited containers

    sudo docker ps -a | grep Exit | cut -d ' ' -f 1 | xargs sudo docker rm

### Remove all images

    for i in `sudo docker images|awk '{print $3}'`;do sudo docker rmi $i;done

