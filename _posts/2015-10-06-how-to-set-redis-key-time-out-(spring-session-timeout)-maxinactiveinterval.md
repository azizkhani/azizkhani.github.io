---
layout: post
title: "how to set redis key time out (spring session timeout) maxInactiveInterval"
comments: true
---
<p>&nbsp;</p>
<p class="p1"><span style="font-size: medium;"><span class="s2">when using spring session in a container when http session is time out session or key that store in redis dose not time out for solve this problem and set timeout or that config like this code&nbsp;</span></span></p>
<p class="p1"><span style="font-size: medium;"><span class="s2"><br /></span></span></p>
<p class="p1"><span style="font-size: medium;"><span class="s2">&lt;</span><span class="s3">bean</span><span class="s4">class</span><span class="s1">=</span>"org.springframework.session.data.redis.config.annotation.web.http.RedisHttpSessionConfiguration"<span class="s4">p:maxInactiveIntervalInSeconds</span><span class="s1">=</span>"180"<span class="s2">/&gt;</span></span></p>
