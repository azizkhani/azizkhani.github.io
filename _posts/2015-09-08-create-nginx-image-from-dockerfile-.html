---
layout: post
title: "create nginx image from Dockerfile "
comments: true
---
<p><span style="font-size: small;">i want to create nginx docker image that i can manage nginx.config</span></p>
<p><span style="font-size: small;">for solve this problem i do it</span></p>
<p><span style="font-size: small;">create <strong>nginx.config</strong> that have this content: in /azizkhani/nginx</span></p>
<p><span style="font-size: small;">events {</span></p>
<p><span style="font-size: small;">&nbsp; worker_connections &nbsp;1024;</span></p>
<p><span style="font-size: small;">}</span></p>
<p><span style="font-size: small;">http {</span></p>
<p><span style="font-size: small;">&nbsp; upstream sessionApp {</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; server localhost:8082;</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; server localhost:8081;</span></p>
<p><span style="font-size: small;">&nbsp; }</span></p>
<p><span style="font-size: small;">&nbsp; server {</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; listen 80;</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; location / {</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; &nbsp; proxy_pass http://sessionApp;</span></p>
<p><span style="font-size: small;">&nbsp; &nbsp; }</span></p>
<p><span style="font-size: small;">&nbsp; }</span></p>
<p><span style="font-size: small;">}&nbsp;</span></p>
<p><span style="font-size: small;">create <strong>DockerFile</strong>(without extension) : in &nbsp;/azizkhani/nginx</span></p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><span style="font-size: small;">FROM nginx</span></p>
<p><span style="font-size: small;">RUN mkdir -p /etc/nginx</span></p>
<p><span style="font-size: small;">COPY nginx.conf /etc/nginx/nginx.conf</span></p>
<p><span style="font-size: small;">and run this command in docker terminal after&nbsp;</span></p>
<p><span style="font-size: small;">cd /azizkhani/nginx</span></p>
<p><span style="font-size: small; line-height: 25.6px; color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; background-color: #f8f8f8;">docker build -t myNginxImage</span></p>
<p><span style="font-size: small;">and after create image&nbsp;</span></p>
<p><span style="font-size: small;">run this command to create container from myNginxImage</span></p>
<div><span style="font-size: small;"><span style="color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 24px; white-space: pre; background-color: #eaeef3;">$ docker run --name container-nginx-name -d -</span><span class="hljs-tag" style="box-sizing: inherit; color: #0048ab; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 24px; white-space: pre;">p</span><span class="hljs-number" style="box-sizing: inherit; color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 24px; white-space: pre;">8080</span><span style="color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 24px; white-space: pre; background-color: #eaeef3;">:</span><span class="hljs-number" style="box-sizing: inherit; color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 24px; white-space: pre;">80 </span><span style="color: #333333; font-family: Consolas, 'Liberation Mono', Courier, monospace; line-height: 25.6px; background-color: #f8f8f8;">myNginxImage</span></span></div>
<div>
<p><span style="font-size: small;">request localhost and nginx show proxy(localhost:8081)</span></p>
</div>
<div><span style="font-size: small;"><br /></span></div>
<div>&nbsp;</div>
