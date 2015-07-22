# Amazon ECS PHP Simple Demo App for Ubuntu 14.04 LTS (Trusty)

Assuming you have install Docker in your machine.

```
$ docker build -t jolks/amazon-ecs-sample .

# The warning message AH00558 can be ignored
$ docker run -p 80:80 jolks/amazon-ecs-sample
AH00558: apache2: Could not reliably determine the server's fully qualified domain name...

# On another terminal:-
$ boot2docker ip
192.168.59.103
```
Open browser and go to http://192.168.59.103 to see the demo page.
```
# To terminate the active container (In this case the Apache web server). On another terminal:-
$ docker ps
CONTAINER ID        IMAGE                     COMMAND                CREATED             STATUS              PORTS                NAMES
7fe637df6bca        jolks/amazon-ecs-sample   "apache2ctl -k resta   4 seconds ago       Up 3 seconds        0.0.0.0:80->80/tcp   lonely_hypatia

$ docker kill 7fe637df6bca

```

## References
* http://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html
* https://docs.docker.com/articles/dockerfile_best-practices/
