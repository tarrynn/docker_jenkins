# Docker jenkins

Dockerfile based off of latest jenkins, on top of which php 5.6, node 9.1.0 and ruby 2.5.0 is installed

### Grabbing the latest image

    docker pull tarrynn/docker_jenkins:latest

### Running the container

    docker run -p 8080:8080 \
	       -p 50000:50000 \
	       -d \
               -v $PWD/jenkins_home:/var/jenkins_me \
               -v /var/run/docker.sock:/var/run/docker.sock \
               -v $(which docker):/usr/bin/docker \
               tarrynn/docker_jenkins:latest


### Exposing to the public

    npm install -g localtunnel
    lt --port 8080

You will be given a https url pointing at port 8080 and you can integrate it with automatic webhooks from external services
