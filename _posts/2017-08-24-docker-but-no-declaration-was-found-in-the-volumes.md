---
layout: post
title: "docker but no declaration was found in the volumes"
comments: true
---
Named volume "db-data:/var/lib/mysql:rw" is used in service "vahed98-mysql" but no declaration was found in the volumes section.
when i want to create docker compose to create container mysql i get this exception 
after add this  

{% highlight yaml %}
volumes:
  db-data:
{% endhighlight %}
it works :D

{% highlight yaml %}

version: '2'
services:
    vahed98-gateway:
        image: vahed98-gateway
        environment:
            - SPRING_PROFILES_ACTIVE=prod,swagger
            - JHIPSTER_SLEEP=10 # gives time for the database to boot before the application
        ports:
            - 80:80
    vahed98-smart-service:
        image: vahed98-smart-service
        environment:
            - SPRING_PROFILES_ACTIVE=prod,swagger
            - JHIPSTER_SLEEP=10 # gives time for the database to boot before the application
        ports:
            - 8082:8082
    vahed98-mysql:
        image: mysql
        environment:
            MYSQL_ROOT_PASSWORD: "rootroot"
            MYSQL_DATABASE: "ihs"
        ports:
            - 3306:3306
        volumes:
            - db-data:/var/lib/mysql/
        networks:
            - overlay
        command: mysqld --lower_case_table_names=1 --skip-ssl --character_set_server=utf8 --explicit_defaults_for_timestamp
volumes:
  db-data:
networks:
  overlay:
{% endhighlight %}
