---
layout: post
title: "الگوریتم رمز نگاری  در جاوا MD5,SHA-256"
comments: true
---
<p>&nbsp;</p>
<p style="text-align: right; padding-left: 60px;"><span style="font-size: medium;">این الگوریتم رمزنگاری در سال ۱۹۹۴ توسط رونالد ویست معرفی شده در زیر یک مثال از این الگوریتم رمزنگاری در زبان جاوا برای استفاده معرفی میشود</span></p>
<p style="text-align: right; padding-left: 60px;"><span style="font-size: small;">&nbsp;</span></p>
<p>&nbsp;</p>
<p>It will use MD5 hashing algorithm to generate a hash value for a password &ldquo;123456&Prime;.</p>
<div class="wp_syntax">
<div class="code">
<pre class="java" style="font-family: monospace;"><span style="color: #000000; font-weight: bold;">package</span> <span style="color: #006699;">com.j2eelist.security</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.security.MessageDigest</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> MD5HashingExample 
<span style="color: #009900;">{</span>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span><span style="color: #000000; font-weight: bold;">throws</span> <span style="color: #003399;">Exception</span>
    <span style="color: #009900;">{</span>
    	<span style="color: #003399;">String</span> password <span style="color: #339933;">=</span> <span style="color: #0000ff;">"123456"</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #003399;">MessageDigest</span> md <span style="color: #339933;">=</span> <span style="color: #003399;">MessageDigest</span>.<span style="color: #006633;">getInstance</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"MD5"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        md.<span style="color: #006633;">update</span><span style="color: #009900;">(</span>password.<span style="color: #006633;">getBytes</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #000066; font-weight: bold;">byte</span> byteData<span style="color: #009900;">[</span><span style="color: #009900;">]</span> <span style="color: #339933;">=</span> md.<span style="color: #006633;">digest</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #666666; font-style: italic;">//convert the byte to hex format method 1</span>
        <span style="color: #003399;">StringBuffer</span> sb <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">StringBuffer</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        <span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">int</span> i <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> i <span style="color: #339933;">&lt;</span> byteData.<span style="color: #006633;">length</span><span style="color: #339933;">;</span> i<span style="color: #339933;">++</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
         sb.<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #003399;">Integer</span>.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">(</span>byteData<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span> <span style="color: #339933;">&amp;</span> 0xff<span style="color: #009900;">)</span> <span style="color: #339933;">+</span> 0x100, <span style="color: #cc66cc;">16</span><span style="color: #009900;">)</span>.<span style="color: #006633;">substring</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">1</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        <span style="color: #009900;">}</span>
&nbsp;
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Digest(in hex format):: "</span> <span style="color: #339933;">+</span> sb.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #666666; font-style: italic;">//convert the byte to hex format method 2</span>
        <span style="color: #003399;">StringBuffer</span> hexString <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">StringBuffer</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    	<span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">int</span> i<span style="color: #339933;">=</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span>i<span style="color: #339933;">&lt;</span>byteData.<span style="color: #006633;">length</span><span style="color: #339933;">;</span>i<span style="color: #339933;">++</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
    		<span style="color: #003399;">String</span> hex<span style="color: #339933;">=</span><span style="color: #003399;">Integer</span>.<span style="color: #006633;">toHexString</span><span style="color: #009900;">(</span>0xff <span style="color: #339933;">&amp;</span> byteData<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   	     	<span style="color: #000000; font-weight: bold;">if</span><span style="color: #009900;">(</span>hex.<span style="color: #006633;">length</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">==</span><span style="color: #cc66cc;">1</span><span style="color: #009900;">)</span> hexString.<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #0000ff;">'0'</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   	     	hexString.<span style="color: #006633;">append</span><span style="color: #009900;">(</span>hex<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">}</span>
    	<span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Digest(in hex format):: "</span> <span style="color: #339933;">+</span> hexString.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">}</span>
<span style="color: #009900;">}</span></pre>
</div>
</div>
<h5>Output</h5>
<div class="wp_syntax">
<div class="code">
<pre class="bash" style="font-family: monospace;">Digest<span style="color: #7a0874; font-weight: bold;">(</span><span style="color: #000000; font-weight: bold;">in</span> hex format<span style="color: #7a0874; font-weight: bold;">)</span>:: e10adc3949ba59abbe56e057f20f883e
Digest<span style="color: #7a0874; font-weight: bold;">(</span><span style="color: #000000; font-weight: bold;">in</span> hex format<span style="color: #7a0874; font-weight: bold;">)</span>:: e10adc3949ba59abbe56e057f20f883e<br /><br /><span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.security.MessageDigest</span><span style="color: #339933;">;</span>
&nbsp;
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> SHAHashingExample 
<span style="color: #009900;">{</span>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span><span style="color: #000000; font-weight: bold;">throws</span> <span style="color: #003399;">Exception</span>
    <span style="color: #009900;">{</span>
    	<span style="color: #003399;">String</span> password <span style="color: #339933;">=</span> <span style="color: #0000ff;">"123456"</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #003399;">MessageDigest</span> md <span style="color: #339933;">=</span> <span style="color: #003399;">MessageDigest</span>.<span style="color: #006633;">getInstance</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"SHA-256"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        md.<span style="color: #006633;">update</span><span style="color: #009900;">(</span>password.<span style="color: #006633;">getBytes</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #000066; font-weight: bold;">byte</span> byteData<span style="color: #009900;">[</span><span style="color: #009900;">]</span> <span style="color: #339933;">=</span> md.<span style="color: #006633;">digest</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #666666; font-style: italic;">//convert the byte to hex format method 1</span>
        <span style="color: #003399;">StringBuffer</span> sb <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">StringBuffer</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        <span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">int</span> i <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span> i <span style="color: #339933;">&lt;</span> byteData.<span style="color: #006633;">length</span><span style="color: #339933;">;</span> i<span style="color: #339933;">++</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
         sb.<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #003399;">Integer</span>.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">(</span>byteData<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span> <span style="color: #339933;">&amp;</span> 0xff<span style="color: #009900;">)</span> <span style="color: #339933;">+</span> 0x100, <span style="color: #cc66cc;">16</span><span style="color: #009900;">)</span>.<span style="color: #006633;">substring</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">1</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
        <span style="color: #009900;">}</span>
&nbsp;
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Hex format : "</span> <span style="color: #339933;">+</span> sb.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
&nbsp;
        <span style="color: #666666; font-style: italic;">//convert the byte to hex format method 2</span>
        <span style="color: #003399;">StringBuffer</span> hexString <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">StringBuffer</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    	<span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">int</span> i<span style="color: #339933;">=</span><span style="color: #cc66cc;">0</span><span style="color: #339933;">;</span>i<span style="color: #339933;">&lt;</span>byteData.<span style="color: #006633;">length</span><span style="color: #339933;">;</span>i<span style="color: #339933;">++</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>
    		<span style="color: #003399;">String</span> hex<span style="color: #339933;">=</span><span style="color: #003399;">Integer</span>.<span style="color: #006633;">toHexString</span><span style="color: #009900;">(</span>0xff <span style="color: #339933;">&amp;</span> byteData<span style="color: #009900;">[</span>i<span style="color: #009900;">]</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   	     	<span style="color: #000000; font-weight: bold;">if</span><span style="color: #009900;">(</span>hex.<span style="color: #006633;">length</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">==</span><span style="color: #cc66cc;">1</span><span style="color: #009900;">)</span> hexString.<span style="color: #006633;">append</span><span style="color: #009900;">(</span><span style="color: #0000ff;">'0'</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
   	     	hexString.<span style="color: #006633;">append</span><span style="color: #009900;">(</span>hex<span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    	<span style="color: #009900;">}</span>
    	<span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Hex format : "</span> <span style="color: #339933;">+</span> hexString.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">}</span>
<span style="color: #009900;">}</span></pre>
</div>
</div>
<h4>Reference</h4>
<p>1. <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">http://en.wikipedia.org/wiki/MD5</a><br /> 2. <a href="http://forums.sun.com/thread.jspa?threadID=5169003" target="_blank">http://forums.sun.com/thread.jspa?threadID=5169003</a></p>
<p><a href="/FILES/2012/08/Md5.java.axdx">Md5.java (625.00 bytes)</a></p>
<p><a href="/FILES/2012/08/SHA256.java.axdx">SHA256.java (633.00 bytes)</a></p>
