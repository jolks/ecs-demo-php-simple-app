# Amazon ECS PHP Simple Demo App for Ubuntu 14.04 LTS (Trusty)

Assuming you have install Docker in your machine:-

```
# Create a Docker Image from Dockerfile locally
$ docker build -t jolks/amazon-ecs-sample .

# To check the image is successfully created
$ docker images
REPOSITORY                TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
jolks/amazon-ecs-sample   latest              59dad6016e14        About an hour ago   279.1 MB
ubuntu                    14.04               d2a0ecffe6fa        12 days ago         188.4 MB

# Run the Docker Image. A running Docker Image is Docker Container.
# A container is an instance of image.
# The warning message AH00558 can be ignored.
$ docker run -p 80:80 jolks/amazon-ecs-sample
AH00558: apache2: Could not reliably determine the server's fully qualified domain name...

# On another terminal:-
$ boot2docker ip
192.168.59.103
```
Open browser and go to http://192.168.59.103 to see the demo page.

To terminate the container (In this case the Apache web server):-
```
# To check all containers or running docker images
$ docker ps
CONTAINER ID        IMAGE                     COMMAND                CREATED             STATUS              PORTS                NAMES
7fe637df6bca        jolks/amazon-ecs-sample   "apache2ctl -k resta   4 seconds ago       Up 3 seconds        0.0.0.0:80->80/tcp   lonely_hypatia

$ docker kill 7fe637df6bca

```

## References
* http://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html
* https://docs.docker.com/articles/dockerfile_best-practices/
* http://stackoverflow.com/questions/23735149/docker-image-vs-container
