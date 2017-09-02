---
layout: post
title: "Custom Hikari Datasource in Spring Boot"
comments: true
---
<p>&nbsp;</p>
<p><span style="font-size: small;">when i using default Spring Boot datasource that create by&nbsp;</span><span style="color: #dd6964; font-family: Monaco; font-size: 11px;">DataSourceAutoConfiguration</span><span style="font-size: small;">&nbsp;hikari pool is correct and max size is ok but i want &nbsp;create custom datasource to set that @primary .</span></p>
<p><span style="font-size: small;">there are some way to create custom Datasource, one of that is</span></p>
<p><span style="font-size: small;"><br /></span></p>
<pre class="brush: java;">@Bean

@ConfigurationProperties(prefix = "spring.datasource")

publicDataSourcedataSource() {

&nbsp; &nbsp; return&nbsp;DataSourceBuilder.create().build();

}</pre>
<p class="p4"><span style="color: #000000;"><br /></span></p>
<p class="p4"><span style="color: #000000;"><br /></span></p>
<pre class="brush: java;">datasource:

&nbsp; &nbsp; &nbsp; &nbsp;&nbsp;jdbc-url:&nbsp;jdbc:mysql://localhost:3306/ihs?useUnicode=yes&amp;characterEncoding=utf8&amp;useSSL=false

&nbsp; &nbsp; &nbsp; &nbsp; username:root

&nbsp; &nbsp; &nbsp; &nbsp; password:pass

&nbsp; &nbsp; &nbsp; &nbsp; hikari:

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;maximum-pool-size:50</pre>
<pre class="brush: java;">&nbsp;</pre>
<pre class="brush: java;">&nbsp;</pre>
<p class="p1"><span style="color: #000000;"><span style="font-size: small;">when create datasource by this way max pool size is not set ,after google, i fount that&nbsp;</span>DataSourceBuilder dose not set Hikari prop&nbsp;</span></p>
<p class="p1">&nbsp;</p>
<p class="p1"><span style="color: #000000;">2017-08-14 22:51:22.844 DEBUG 31814 --- [l-1 housekeeper] com.zaxxer.hikari.pool.HikariPool<span class="Apple-converted-space">&nbsp; &nbsp; &nbsp; &nbsp; </span>: HikariPool-1 - Pool stats (total=<span style="font-size: medium;">10</span>, active=0, idle=50, waiting=0)</span></p>
<p><span style="font-size: small;">Another way for create custom datasource is like this :</span></p>
<p>&nbsp;</p>
<p>&nbsp;<span style="color: #ffffff; font-family: Monaco; font-size: 11px;">@Bean</span></p>
<pre class="brush: java;">@Primary

@ConfigurationProperties("spring.datasource.hikari")

publicDataSourcePropertiesdataSourceProperties() {

&nbsp; &nbsp; returnnewDataSourceProperties();

}

&nbsp;

@Bean

@Primary

@ConfigurationProperties("spring.datasource.hikari")

publicDataSourcedataSource() {

&nbsp; &nbsp; returndataSourceProperties().initializeDataSourceBuilder().build();

}</pre>
<pre class="brush: java;">&nbsp;</pre>
<p class="p1"><span style="color: #000000;">2017-08-14 22:51:22.844 DEBUG 31814 --- [l-1 housekeeper] com.zaxxer.hikari.pool.HikariPool<span class="Apple-converted-space">&nbsp; &nbsp; &nbsp; &nbsp; </span>: HikariPool-1 - Pool stats (total=<span style="font-size: medium;">50</span>, active=0, idle=50, waiting=0)</span></p>
<p>&nbsp;</p>
