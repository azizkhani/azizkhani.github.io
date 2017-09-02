---
layout: post
title: "spring security oauth2 change default prefix path"
comments: true
---
<p><span style="font-size: medium;">when add oauth to your project&nbsp;</span></p>
<p><span style="font-size: medium;">oauth library create some endpoint for get token .get authorize code ,get refresh token and some other oauth protocol</span></p>
<p><span style="font-size: medium;">this endpoint has rest url s in this url</span></p>
<p>&nbsp;</p>
<p class="p1"><span style="font-size: small;">Mapped "{[/oauth/authorize]}</span></p>
<p class="p1">&nbsp;</p>
<p class="p1"><span style="font-size: small;">Mapped "{[/oauth/token],methods=[GET]}"</span></p>
<p class="p1">&nbsp;</p>
<p class="p1"><span style="font-size: small;">Mapped "{[/oauth/check_token]}"</span></p>
<p class="p1"><span style="font-size: small;">,..</span></p>
<p class="p1">&nbsp;</p>
<p class="p1"><span style="font-size: small;">when your project run in root servlet-path every thing is ok .but when using servlet-path:/api or other name&nbsp;</span></p>
<p class="p1"><span style="font-size: small;">request to /api/oauth/token for get token is get exception</span></p>
<p class="p1"><span style="font-size: small;"><br /></span></p>
<p class="p1"><span style="font-size: small;">for solve this problem need to change default configuration for oauth path for change it nee write this configuration code</span></p>
<p class="p1"><span style="font-size: small;"><br /></span></p>
<p class="p1"><span style="color: #000080;">@Override</span></p>
<p class="p2"><span style="color: #000080;"><span class="s1">public</span> <span class="s1">void</span> configure(AuthorizationServerEndpointsConfigurer <span class="s2">endpoints</span>) <span class="s1">throws</span> Exception {</span></p>
<p class="p2"><span style="color: #000080;"><strong><span class="s2">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; endpoints</span>.prefix(<span class="s3">"/api"</span>)</strong>.authenticationManager(<span class="s6">authenticationManager</span>).userDetailsService(<span class="s6">userDetailsService</span>).</span></p>
<p class="p2"><span style="color: #000080;">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; accessTokenConverter(jwtAccessTokenConverter());</span></p>
<p class="p1">&nbsp;</p>
<p class="p2"><span style="color: #000080;">}&nbsp;</span></p>
<p><span style="font-size: medium;"><br /></span></p>
