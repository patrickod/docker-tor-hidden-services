# Docker tor hidden services

This docker container allows you to easily expose ports on other containers as hidden services on the tor network.

## Usage

Lets say you have docker container running a web app that you want to expose as a hidden service on the tor network. In this container's Dockerfile it contains the following instruction.

```
EXPOSE 80
```

Running this as a hidden service is as simple as the following two commands

```bash
$ docker run -d my-awesome-app
$ docker run --link my-hidden-web-app:web -d patrickod/docker-tor-hidden-service
```

This will expose port 80 on the hidden service domain and direct it to your linked container.

## Why ?

Two reasons mainly.

The more traffic the tor network has the more resilient it becomes to statistical correlation attacks.

Hidden services are a hugely important feature of the tor network and I wanted to make them more readily accessible to the world. By removing any slight configuration overhead I'm hoping to encourage their widespread use. They're incredibly useful even in situations where anonymity is not the main objective. Using hidden services to break NAT is also a common use case for example

