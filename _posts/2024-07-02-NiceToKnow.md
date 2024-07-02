---
title: 'Git Nice To Know'
date: 2021-11-16
permalink: /posts/2021/11/2024-07-02-NiceToKnow/
tags:
  - Docker
  - Git
--- 

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

Git Nice To Know
---------------- 

1. Error message: Filename too long during git clone of repository. 
    Solution: Run the following code inside cmd as an administrator. 

    ````shell
    git config --system core.longpaths true
    `````

    If this does not work, run the following during clone of repo.

    ````shell
    git clone -c core.longpaths=true <repo-url>
    `````