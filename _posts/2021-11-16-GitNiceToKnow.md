---
title: 'Git Nice To Know'
date: 2021-11-16
permalink: /posts/2021/11/2021-11-16-GitNiceToKnow/
tags:
  - Git
  - Debugging
---

Solutions to common errors I have encountered while working on various software projects. 

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