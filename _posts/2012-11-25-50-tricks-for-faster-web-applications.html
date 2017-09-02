---
layout: post
title: "50 Tricks for Faster Web Applications"
comments: true
---
<div id="newsContent">
<p><a href="http://channel9.msdn.com/Events/Speakers/jatinder-mann">Jatinder Mann</a>, an Internet Explorer PM at Microsoft, held the session <a href="http://channel9.msdn.com/Events/Build/2012/3-132?format=html5">50 performance tricks to make your HTML5 apps and sites faster</a>&nbsp;at BUILD 2012, providing many tips for creating faster web applications.</p>
<p>The advice provided by Mann was organized around&nbsp;six principles outlined below.</p>
<p><strong>1.&nbsp;Quickly Respond to Network Requests.</strong></p>
<ul>
<li>Avoid Redirections. 63% of the top 1,000 websites use redirections. They could increase the speed of their pages by 10% by not performing a redirect.</li>
<li>Avoid <a href="http://en.wikipedia.org/wiki/Meta_refresh">Meta-refresh</a>. 14% of the world&rsquo;s URLs use meta-refreshes.</li>
<li>Minimize server response time by using CDNs located as close as possible to the user</li>
<li>Maximize the usage of concurrent connections by downloading resources from different domains</li>
<li>Reuse connections. Don&rsquo;t close the connection when responding to a request.</li>
<li>Make sure data served by partner sites&nbsp;is not delaying page load</li>
<li>Understand the network timing components&nbsp;&ndash;Redirect, Cache, DNS, Request, Response, etc.&nbsp;&ndash;. Use the <a href="http://msdn.microsoft.com/en-us/library/ie/hh673552%28v=vs.85%29.aspx">Navigation Timing API</a>&nbsp;on IE 9&amp;10 to measure the time spent by the browser on each operation.</li>
</ul>
<p><strong>2. Minimize Bytes Downloaded.</strong>&nbsp;Minimize the amount of data downloaded when a web page is loaded. The average website downloads 777KB of data out of which&nbsp;474KB being images, 128KB scripts, and 84KB Flash.</p>
<ul>
<li>Request gzipped content</li>
<li>Keep resources locally in packages, such as the <a href="http://msdn.microsoft.com/en-us/library/windows/apps/hh694557.aspx">Package Resource Index</a> generated for the Windows Store apps. That way they are readily available when necessary.</li>
<li>Cache dynamic resources in&nbsp;HTML5 App Cache. This cache downloads the resources only once avoiding multiple network trips.&nbsp;The cache&nbsp;automatically re-downloads resources when the version of the application changes.</li>
<li>Provide cacheable content whenever possible by using the &ldquo;Expires&rdquo;&nbsp;field in the response.</li>
<li>Use conditional requests by setting the <a href="http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html">If-Modified-Since</a> field of the request.&nbsp;</li>
<li>Cache data requests&nbsp;&ndash;HTTP, XML, JSON, etc.&nbsp;&ndash; because about 95-96% of the requests don&rsquo;t change over the day. Although a reasonable idea, less than 1% of the websites cache the requests received.</li>
<li>Standardize file naming capitalization. While a server may recognize Icon.jpg as icon.jpg, they are different resources for the web platform, generating different network requests.</li>
</ul>
<p><strong>3. Efficiently Structure Markup.</strong>&nbsp;For IE use the latest markup standardization since it is the fastest. Earlier IE6-IE9 markup styles are recognized by IE 10 but they are not as fast as the latest one.</p>
<ul>
<li>Use the HTTP header field &ldquo;X-UA-Compatible: IE=EmulateIE7&rdquo; instead of the HTML tag &lt;meta http-equiv="X-UA-Compatible" content="IE=EmulateIE7"&gt; to force IE run in a legacy mode that might be needed for certain business web applications. It&rsquo;s faster that way.</li>
<li>Stylesheets should be linked at the top of the page inside the &lt;head&gt;, after the &lt;title&gt; in order to provide a smooth rendering.</li>
<li>Stylesheets should never be linked at the bottom of the page. The page may be flashing while loading.</li>
<li>Avoid <a href="mailto:%E2%80%9C@import">&ldquo;@import</a>&rdquo; for hierarchical styles because it synchronously blocks the creation of CSS data structures and screen painting.</li>
<li>Avoid embedded and inline styles because it forces the browser to make a context switch between the HTML and CSS parsers.</li>
<li>Only include the necessary styles. Avoid downloading and parsing style that won&rsquo;t be used.</li>
<li>Link JavaScript only at the bottom of the page. This makes sure that the images, CSS, etc. are already loaded so the scripts can do they job without waiting on the resources, and avoiding context switching.</li>
<li>Do not link JavaScript in the head of the page. Use the &ldquo;defer&rdquo; attribute if some scripts must be loaded at the beginning.</li>
<li>Avoid inline JavaScript to avoid context switching.</li>
<li>Use the &ldquo;async&rdquo; attribute to load JavaScript to make the entire script loading and executing asynchronous.</li>
<li>Avoid duplicate code. 52% of the world&rsquo;s web pages&nbsp;contain 100 lines or more of duplicate code such as linking a JavaScript file twice.</li>
<li>Standardize on one JS framework, be it jQuery, Dojo, Prototype.js, etc.. The browser won&rsquo;t have to load multiple frameworks that provide basically the same functionality.</li>
<li>Don&rsquo;t load scripts&nbsp;&ndash;FB, Twitter, etc. - just to be cool. They compete for resources.</li>
</ul>
<p><strong>4. Optimize Media Usage</strong>. Images are the most utilized resource, on average a website downloading 58 images.</p>
<ul>
<li>Avoid downloading too many images, keeping their number to maximum 20-30 due to page load time.</li>
<li>Use image sprites to combine multiple images into one. This technique reduces the number of network connections, and the number of bytes downloaded and GPU cycles.</li>
<li>Create image sprites by hand because tools may leave large empty spaces leading to larger downloads and more GPU cycles.</li>
<li>Use PNG: best compromise between download size, decoding time, compatibility, and compression rate. JPEG may be used for photographs.</li>
<li>Use the native image resolution to avoid unnecessary bytes download and CPU processing for scaling.</li>
<li>Replace images with CSS3 gradients when possible.</li>
<li>Replace images with CSS3&nbsp;border radius&nbsp;when possible.</li>
<li>Use CSS3 transforms to create move, rotate or skew effects.</li>
<li>Use <a href="http://en.wikipedia.org/wiki/Data_URI_scheme">Data URI</a> for small single images. It saves an image download.</li>
<li>Avoid complex SVGs which require longer downloads and processing.</li>
<li>Specify an image preview when including an HTML5. The browser won&rsquo;t have to download the entire video to figure out what the preview image should be.</li>
<li>Use HTML5 instead of Flash, Silverlight, or QuickTime. HTML5 is faster and the plug-in runtime takes system resources.</li>
<li>Proactively download rich media asynchronously and keep it in the app cache.</li>
</ul>
<p><strong>5. Write Fast JavaScript.</strong></p>
<ul>
<li>Use Integers when doing math operations in JavaScript, if possible. Floating point operations take much longer in JavaScript than their corresponding&nbsp;integer operations. Convert floating points into integers with Math.floor and Math.ceil, especially for computationally intensive operations.</li>
<li>Minify JavaScript code for smaller downloads and better runtime performance.</li>
<li>Initialize JS on demand. Load JS dynamically when needed.</li>
<li>Minimize DOM interactions by caching variable such as document, body, etc.</li>
<li>Use the built-in DOM code such as element.firstChild or node.nextSibling. They are highly optimized, better than what a third party library might provide.</li>
<li>Use querySelectorAll for accessing a large number of DOM elements.</li>
<li>Use .innerHTML to construct dynamic pages.</li>
<li>Batch markup changes.</li>
<li>Maintain a Small and Healthy DOM&nbsp;&ndash;&nbsp;maximum 1,000 elements.</li>
<li>JSON is faster than XML.</li>
<li>Use the browser&rsquo;s JSON native methods.</li>
<li>Don&rsquo;t abuse the usage of regular expressions.</li>
</ul>
<p><strong>6. Know What Your Application is Doing</strong></p>
<ul>
<li>Understand JavaScript timers: setTimeout and clearInterval. Don&rsquo;t let timers run unless you use them for something. Also, combine timers.</li>
<li>Align timers to the display frame at 16.7 ms if the monitor refreshes at 60Hz.</li>
<li>Use requestAnimationFrame for animations to do graphics work in IE 10/Chrome/Firefox. It makes a call back when it is the time to paint, so there is no need&nbsp;for a timer.</li>
<li>Use the visibility API (document.hidden, Visibilityhange)&nbsp;to determine the visibility state of the application, and throttle down activity when the page is hidden.&nbsp;Saves CPU and battery life.</li>
</ul>
<p>Mann recommended using <a href="http://msdn.microsoft.com/en-us/performance/cc825801.aspx">Windows Performance Tools</a>&nbsp;to measure the performance of web pages in IE and optimizing pages for less CPU time&nbsp;and increasing parallelism.</p>
</div>
<p>&nbsp;</p>
