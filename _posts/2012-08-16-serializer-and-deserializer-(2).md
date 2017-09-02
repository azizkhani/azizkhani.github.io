---
layout: post
title: "Serializer and Deserializer (2)"
comments: true
---
<p style="text-align: right;"><span style="font-size: medium;">تا به حال به این دو کلمه در زبان جاوا برخوردید و کاربرد آن را میدانید </span></p>
<p style="text-align: right;"><span style="font-size: medium;">گاهی اوقات بیش میباد که احتیاج به ذخیره یک شی به صورت فایل است تا بعدا همون شی را بتون بازیابی کرد </span></p>
<p style="text-align: right;"><span style="font-size: medium;">مثال زیر این امر را تفهیم میکنه</span></p>
<h4><span style="font-size: medium;">Deserializer.java</span></h4>
<p>&nbsp;</p>
<p>This class will read a serialized file &ldquo;c:\\address.ser&rdquo; &ndash; created in <a href="http://azizkhani.net/post/2012/08/16/Serializer-and-Deserializer-%281%29.aspx" target="_blank">this example</a>, and convert it back to &ldquo;Address&rdquo; object and print out the saved value.</p>
<p>&nbsp;</p>
<div class="wp_syntax">
<div class="code">
<pre class="java" style="font-family: monospace;"><span style="color: #000000; font-weight: bold;">package</span> <span style="color: #006699;">com.j2eelist.io</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.FileInputStream</span><span style="color: #339933;">;</span>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.ObjectInputStream</span><span style="color: #339933;">;</span>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.Serializable</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Deserializer<span style="color: #009900;">{</span>
&nbsp;
   <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main <span style="color: #009900;">(</span><span style="color: #003399;">String</span> args<span style="color: #009900;">[</span><span style="color: #009900;">]</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
&nbsp;
	   Deserializer deserializer <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> Deserializer<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   Address address <span style="color: #339933;">=</span> deserializer.<span style="color: #006633;">deserialzeAddress</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
	   <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>address<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   <span style="color: #009900;">}</span>
&nbsp;
   <span style="color: #000000; font-weight: bold;">public</span> Address deserialzeAddress<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">{</span>
&nbsp;
	   Address address<span style="color: #339933;">;</span>
&nbsp;
	   <span style="color: #000000; font-weight: bold;">try</span><span style="color: #009900;">{</span>
&nbsp;
		   <span style="color: #003399;">FileInputStream</span> fin <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileInputStream</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"c:<span style="color: #000099; font-weight: bold;">\\</span>address.ser"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
<span style="font-size: medium; color: #ff0000;"> ObjectInputStream ois = <span style="font-weight: bold;">new</span> ObjectInputStream(fin);</span>
		   address <span style="color: #339933;">=</span> <span style="color: #009900;">(</span>Address<span style="color: #009900;">)</span> ois.<span style="color: #006633;">readObject</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
		   ois.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
		   <span style="color: #000000; font-weight: bold;">return</span> address<span style="color: #339933;">;</span>
&nbsp;
	   <span style="color: #009900;">}</span><span style="color: #000000; font-weight: bold;">catch</span><span style="color: #009900;">(</span><span style="color: #003399;">Exception</span> ex<span style="color: #009900;">)</span><span style="color: #009900;">{</span>
		   ex.<span style="color: #006633;">printStackTrace</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
		   <span style="color: #000000; font-weight: bold;">return</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #339933;">;</span>
	   <span style="color: #009900;">}</span> 
   <span style="color: #009900;">}</span> 
<span style="color: #009900;">}</span></pre>
</div>
</div>
<p>&nbsp;</p>
