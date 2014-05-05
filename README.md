docker-commands on ubuntu
===============


### Remove all containers

    sudo docker.io rm `sudo docker.io ps --no-trunc -a -q`

### Remove all images

    for i in `sudo docker.io images|grep \<none\>|awk '{print $3}'`;do sudo docker.io rmi $i;done
