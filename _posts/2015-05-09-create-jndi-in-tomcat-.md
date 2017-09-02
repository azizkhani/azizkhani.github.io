---
layout: post
title: "create jndi in tomcat "
comments: true
---
<h2>Create META-INF/context.xml</h2>
<p><span style="font-size: small;">&lt;Context&nbsp; docBase="appName" path="/" reloadable="true" &gt;</span><br /><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &lt;Resource name="develop" auth="Container" type="javax.sql.DataSource" maxActive="50&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; maxIdle="30" maxWait="10000" username="test"&nbsp;&nbsp;&nbsp; password="test"</span><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; driverClassName="oracle.jdbc.OracleDriver" url="jdbc:oracle:thin:@192.168.36.250:1521:XE" /&gt;</span><br /><br /><span style="font-size: small;">&lt;/Context&gt;</span></p>
<p>&nbsp;</p>
<h2>web.xml configuration</h2>
<p>&nbsp;</p>
<p><span style="font-size: small;">&lt;resource-ref&gt;</span><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &lt;description&gt;jdbc Datasource example&lt;/description&gt;</span><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &lt;res-ref-name&gt;develop&lt;/res-ref-name&gt;</span><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &lt;res-type&gt;javax.sql.DataSource&lt;/res-type&gt;</span><br /><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &lt;res-auth&gt;Container&lt;/res-auth&gt;</span><br /><span style="font-size: small;">&nbsp; &nbsp;&nbsp;&nbsp; &lt;/resource-ref&gt;</span></p>
