---
layout: post
title: "Serializer and Deserializer (1)"
comments: true
---
<p style="text-align: right;"><span style="font-size: medium;">تا به حال به این دو کلمه در زبان جاوا برخوردید و کاربرد آن را میدانید </span></p>
<p style="text-align: right;"><span style="font-size: medium;">گاهی اوقات بیش میباد که احتیاج به ذخیره یک شی به صورت فایل است تا بعدا همون شی را بتون بازیابی کرد </span></p>
<p style="text-align: right;"><span style="font-size: medium;">مثال زیر این امر را تفهیم میکنه</span></p>
<h1 class="post-title">How to write an Object to file in Java</h1>
<h4><span style="font-size: medium;">1. Address.java</span></h4>
<p>Create an &ldquo;Address&rdquo; object and implement <strong>Serializable interface</strong>. This object is going to write into a file.</p>
<div class="wp_syntax">
<div class="code">
<pre class="java" style="font-family: monospace;"><span style="color: #000000; font-weight: bold;">package</span> <span style="color: #006699;">com.j2eelist.io</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.Serializable</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Address <span style="color: #000000; font-weight: bold;">implements</span> <span style="color: #003399;">Serializable</span><span style="color: #009900;">{</span>
&nbsp;
	   <span style="color: #003399;">String</span> street<span style="color: #339933;">;</span>
	   <span style="color: #003399;">String</span> country<span style="color: #339933;">;</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> setStreet<span style="color: #009900;">(</span><span style="color: #003399;">String</span> street<span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   <span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">street</span> <span style="color: #339933;">=</span> street<span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> setCountry<span style="color: #009900;">(</span><span style="color: #003399;">String</span> country<span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   <span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">country</span> <span style="color: #339933;">=</span> country<span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #003399;">String</span> getStreet<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   <span style="color: #000000; font-weight: bold;">return</span> <span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">street</span><span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #003399;">String</span> getCountry<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   <span style="color: #000000; font-weight: bold;">return</span> <span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">country</span><span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
&nbsp;
	   @Override
	   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #003399;">String</span> toString<span style="color: #009900;">(</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
    	   <span style="color: #000000; font-weight: bold;">return</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">StringBuffer</span><span style="color: #009900;">(</span><span style="color: #0000ff;">" Street : "</span><span style="color: #009900;">)</span>
    	   .<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">street</span><span style="color: #009900;">)</span>
    	   .<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #0000ff;">" Country : "</span><span style="color: #009900;">)</span>
    	   .<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">country</span><span style="color: #009900;">)</span>.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
&nbsp;
<span style="color: #009900;">}<br /><br /></span></pre>
<h4><span style="font-size: medium;">2. Serializer.java</span></h4>
<p>This class will write the &ldquo;Address&rdquo; object and it&rsquo;s variable value (&ldquo;wall street&rdquo;, &ldquo;united state&rdquo;) into a file named &ldquo;address.ser&rdquo;, locate in c drive.</p>
<div class="wp_syntax">
<div class="code">
<pre class="java" style="font-family: monospace;"><span style="color: #000000; font-weight: bold;">package</span> <span style="color: #006699;">com.j2eelist.io</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.FileOutputStream</span><span style="color: #339933;">;</span>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.ObjectOutputStream</span><span style="color: #339933;">;</span>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.Serializable</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Serializer <span style="color: #009900;">{</span>
&nbsp;
   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main <span style="color: #009900;">(</span><span style="color: #003399;">String</span> args<span style="color: #009900;">[</span><span style="color: #009900;">]</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
&nbsp;
	   Serializer serializer <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> Serializer<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   serializer.<span style="color: #006633;">serializeAddress</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"wall street"</span>, <span style="color: #0000ff;">"united state"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   <span style="color: #009900;">}</span>
&nbsp;
   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> serializeAddress<span style="color: #009900;">(</span><span style="color: #003399;">String</span> street, <span style="color: #003399;">String</span> country<span style="color: #009900;">)</span><span style="color: #009900;">{</span>
&nbsp;
	   Address address <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> Address<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   address.<span style="color: #006633;">setStreet</span><span style="color: #009900;">(</span>street<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   address.<span style="color: #006633;">setCountry</span><span style="color: #009900;">(</span>country<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">try</span><span style="color: #009900;">{</span>
&nbsp;
		<span style="color: #003399;">FileOutputStream</span> fout <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileOutputStream</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"c:<span style="color: #000099; font-weight: bold;">\\</span>address.ser"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
<span style="font-size: medium;"> <span style="color: #ff0000;"><em> ObjectOutputStream</em></span> oos <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #ff0000;">ObjectOutputStream</span><span style="color: #009900;">(</span>fout<span style="color: #009900;">)</span><span style="color: #339933;">;</span> </span> 
		oos.<span style="color: #006633;">writeObject</span><span style="color: #009900;">(</span>address<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
		oos.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
		<span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Done"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
	   <span style="color: #009900;">}</span><span style="color: #000000; font-weight: bold;">catch</span><span style="color: #009900;">(</span><span style="color: #003399;">Exception</span> ex<span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   ex.<span style="color: #006633;">printStackTrace</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span>
   <span style="color: #009900;">}</span>
<span style="color: #009900;">}</span></pre>
</div>
</div>
<pre class="java" style="font-family: monospace;">&nbsp;</pre>
</div>
</div>
