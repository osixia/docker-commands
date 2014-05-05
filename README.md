docker-commands on ubuntu
===============

### Stop all containers

    sudo docker.io stop $(sudo docker.io ps -a -q)

### Remove all containers

    sudo docker.io rm $(sudo docker.io ps -a -q)

### Remove all images

    for i in `sudo docker.io images|grep \<none\>|awk '{print $3}'`;do sudo docker.io rmi $i;done
