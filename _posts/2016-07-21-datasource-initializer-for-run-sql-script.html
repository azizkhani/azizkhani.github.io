---
layout: post
title: "datasource Initializer for run sql script"
comments: true
---
<p><span style="font-size: medium;">some time our application have initial data or sometimes needs to run sql script to create tables or other database object when application init.</span></p>
<p>&nbsp;</p>
<p><span style="font-size: medium;">in this code when can do that very simple and easy by spring boot&nbsp;</span></p>
<p>&nbsp;</p>
<p class="p1">@Inject</p>
<p class="p2"><span class="s1">private</span>&nbsp;DataSource&nbsp;<span class="s2">dataSource</span>;</p>
<p class="p2">&nbsp;</p>
<p class="p4"><span class="s4">@Value</span><span class="s3">(</span>"classpath:schema.sql"<span class="s3">)</span></p>
<p>&nbsp;<span class="s1">private</span><span class="s3">&nbsp;Resource&nbsp;</span>schemaScript<span class="s3">;</span></p>
<p class="p5"><span class="s3"><br /></span></p>
<p class="p1">@Bean</p>
<p class="p2"><span class="s1">public</span>&nbsp;DataSourceInitializer dataSourceInitializer(<span class="s1">final</span>&nbsp;DataSource&nbsp;<span class="s2">dataSource</span>) {</p>
<p class="p2"><span class="s1">&nbsp;&nbsp;&nbsp; &nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s1">final</span>&nbsp;DataSourceInitializer&nbsp;<span class="s2">initializer</span>&nbsp;=&nbsp;<span class="s1">new</span>&nbsp;DataSourceInitializer();</p>
<p class="p3">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp;initializer<span class="s3">.setDataSource(</span>dataSource<span class="s3">);</span></p>
<p class="p2"><span class="s2">&nbsp; &nbsp;&nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s2">initializer</span>.setDatabasePopulator(databasePopulator());</p>
<p class="p3"><span class="s1">&nbsp; &nbsp;&nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s1">return</span>initializer<span class="s3">;</span></p>
<p class="p2">}</p>
<p class="p2"><span class="s1">private</span>&nbsp;DatabasePopulator databasePopulator() {</p>
<p class="p2"><span class="s1">&nbsp; &nbsp;&nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s1">final</span>&nbsp;ResourceDatabasePopulator&nbsp;<span class="s2">populator</span>&nbsp;=&nbsp;<span class="s1">new</span>&nbsp;ResourceDatabasePopulator();</p>
<p class="p2"><span class="s2">&nbsp; &nbsp;&nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s2">populator</span>.addScript(<span class="s4">schemaScript</span>);</p>
<p class="p3"><span class="s1">&nbsp; &nbsp;&nbsp;</span>&nbsp;&nbsp; &nbsp;<span class="s1">return</span>populator<span class="s3">;</span></p>
<p class="p5">&nbsp;</p>
<pre class="brush: java;">}&nbsp;</pre>
