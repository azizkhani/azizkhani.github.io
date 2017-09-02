---
layout: post
title: "jQuery Full Screen Facebook Like"
comments: true
---
<div style="overflow: hidden; color: #000000; background-color: #ffffff; text-align: left; text-decoration: none;">
<pre class="brush: js;">&lt;!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"&gt;
    &lt;html&gt;
    &lt;head&gt;
    &lt;title&gt;jaspreetchahal.org&lt;/title&gt;
    &lt;script src="https://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"&gt;&lt;/script&gt;
    &lt;/head&gt;
    &lt;body &gt;
    &lt;a href="javascript:void(0)" id="fullscreen"&gt;full screen&lt;/a&gt;
    &lt;script&gt;
    $("#fullscreen").bind("click", function() {
    var elem = document.getElementById("img"),
    req = elem.requestFullScreen || elem.webkitRequestFullScreen || elem.mozRequestFullScreen ;
    req.call(elem);
    });
    &lt;/script&gt;
    &lt;img src="/path/to/your/img" id="img" /&gt;
    &lt;/body&gt;
    &lt;/html&gt;</pre>
<br class="sy0" />Read more: <a style="color: #003399;" href="http://jaspreetchahal.org/jquery-full-screen-facebook-like/#ixzz27n7G2yLD">http://jaspreetchahal.org/jquery-full-screen-facebook-like/#ixzz27n7G2yLD</a></div>
