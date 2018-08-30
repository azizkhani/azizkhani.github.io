---
layout: post
published: true
title: 'docker dose not start in CentOS '
---
## change this configuration

bash # cat  /etc/sysconfig/docker-storage
DOCKER_STORAGE_OPTIONS="--storage-driver devicemapper "

bash # cat  /etc/sysconfig/docker-storage-setup
STORAGE_DRIVER=devicemapper
