---
layout: post
title: "Spring Security (redirecting to "/favicon.ico" after login )"
comments: true
---
<p>The issue is, when the browser cache is empty and a user comes in, here is what happens:</p>
<ul>
<li>the user requests URL "/". This URL is cached.</li>
<li>the browser makes a requests to "/favicon.ico". This URL becomes the new URL where to redirect to upon authentication.</li>
<li>the user posts the login form and is redirected to "/favicon.ico".</li>
</ul>
<p>To fix this, you need to set "/favicon.ico" as being a non-secured resources:<br /><br /><span style="font-family: Courier New; font-size: 12px;">&lt;intercept-url pattern="/favicon.ico" access="ROLE_ANONYMOUS" /&gt;</span></p>
