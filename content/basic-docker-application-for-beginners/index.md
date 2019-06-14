---
title: "Basic Docker application for beginners"
description: "Github. “Basic Docker application for beginners” is published by React Engineer"
date: "2018-09-27T16:41:20.299Z"
categories: 
  - Docker
  - Nodejs
  - Dockerfiles

published: true
canonical_link: https://medium.com/@reactjavascript/basic-docker-application-for-beginners-572870386b72
redirect_from:
  - /basic-docker-application-for-beginners-572870386b72
---

**Github**

[https://github.com/balramsinghindia/node-docker-boilerplate](https://github.com/balramsinghindia/node-docker-boilerplate)

Create sample folder with name demo

_mkdir demo_

_cd demo_

vim Dockerfile

**Dockerfile**

_FROM node:latest_

_COPY package.json demo/package.json_

_RUN cd /demo && npm install_

vim package.json

**Sample package.json**

_{  
 “name”: “Docker file”,  
 “version”: “1.0.0”,  
 “dependencies”: {  
 “es6-promise”: “4.1.1”,  
 “whatwg-fetch”: “2.0.3”  
 }  
}_

**Build docker**

_docker build -t some-name:v2 ._

**List all Docker images**

_docker images_

**List running docker and see ports**

_docker ps_

**Run docker**

_docker run -ti somename:v1 bash_

We can publish docker in dockerhub.com.

**Login in DockerHub**

_docker login (Use Docker Hub credentials)_

**Create a docker in DockerHub and pull it in your local**

_docker pull balramsingh/modules_

**Push local docker to DockerHub**

_docker push balramsingh/modules:v1_

**Port Mapping**

Map docker application port with your docker port.

_docker run -p 9500:5000 -ti -w /demo balramsingh/modules:v1 npm start_

Here 9500 in local port and 5000 is docker port.

**Reference:**

Top 10 Docker CLI commands you can’t live without

[https://medium.com/the-code-review/top-10-docker-commands-you-cant-live-without-54fb6377f481](https://medium.com/the-code-review/top-10-docker-commands-you-cant-live-without-54fb6377f481)
