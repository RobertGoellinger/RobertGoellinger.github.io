---
title: 'Git Nice To Know'
date: 2021-11-16
permalink: /posts/2021/11/2021-11-16-NiceToKnow/
tags:
  - Docker
  - Debugging
---

Solutions to common errors I have encountered while working on various software projects. 

Docker Nice to know
-------------------

1. Docker builds may only access directories that are below the build context directory. If you need to include a dependency from above the build directory there different solutions: 
    * Run this from the same directory level of the dependency you want to include: 
        ````shell
        docker build -t app -f ai-service/Dockerfile .
        ````
        
    * In docker-compose this might look like this: 
        ````shell
        ai-service: 
            container_name: ai-service
            build: 
                context: ../
                dockerfile: ai-service/Dockerfile
        ````