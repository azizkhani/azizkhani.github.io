---
layout: post
title: "maven test"
comments: true
---
<p>go to directory that have .pom</p>
<p>write this line</p>
<pre class="lang-java prettyprint"><code><span class="pln">mvn </span><span class="pun">-</span><span class="typ">Dtest</span><span class="pun">=TestApp1</span><span class="pun">#testPrintHelloWorld</span></code><code><span class="pln"> test<br /><br /><br /></span></code></pre>
<pre class="brush: java;">package com.core;
 
public class App {
	public static void main(String[] args) {
 
		System.out.println(getHelloWorld());
 
	}
 
	public static String getHelloWorld() {
 
		return "Hello World";
 
	}
 
	public static String getHelloWorld2() {
 
		return "Hello World 2";
 
	}
}<br /><br /><br /></pre>
<pre class="brush: java;">package com.core;
 
import junit.framework.Assert;
import org.junit.Test;
 
public class TestApp1 {
 
	@Test
	public void testPrintHelloWorld() {
 
		Assert.assertEquals(App.getHelloWorld(), "Hello World");
 
	}
 
}<br /><br /><br /><a href="http://maven.apache.org/index.html">http://maven.apache.org/index.html</a></pre>
