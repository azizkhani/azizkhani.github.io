---
layout: post
title: "docker but no declaration was found in the volumes"
comments: true
---
<p></p>
<p class="p1"><span class="s1">Named volume "db-data:/var/lib/mysql:rw" is used in service "vahed98-mysql" but no declaration was found in the volumes section.</span></p>
<p class="p1"><span class="s1"><br /></span></p>
<p class="p1"><span class="s1">when i want to create docker compose to create container mysql i get this exception&nbsp;</span></p>
<p class="p1"><span class="s1">after add this &nbsp;</span></p>


<p class="p1"><strong style="color: #ff0000;"><span style="font-variant-ligatures: no-common-ligatures;">volumes:</span></strong></p>
<p class="p1"><span style="color: #ff0000;"><strong><span style="font-variant-ligatures: no-common-ligatures;">&nbsp; db-data:</span></strong></span></p>
<p class="p1"><span class="s1"><br /></span></p>
<p class="p1"><span class="s1"><br /></span></p>
<p class="p1"><span class="s1">it works :D</span></p>

{% highlight docker %}


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
