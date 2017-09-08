---
layout: post
published: true
title: docker compose port
subtitle: docker compose port
---
## docker compose port

docker compose allow to expose port like this 


ports (HOST:CONTAINER),


        version: "2"
        services:
            vahed98-gateway:
                image: vahed98-gateway
                environment:
                    - SPRING_PROFILES_ACTIVE=prod,swagger
                    - ZUUL_ROUTES_APP_URL= http://vahed98-smart-service:8082/app/
                    - JHIPSTER_SLEEP=10 # gives time for the database to boot before the application
                ports:
                    - 8080:80
                depends_on:
                    - "vahed98-smart-service"
