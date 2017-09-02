---
layout: post
title: "localStorage JSON"
comments: true
---
<p><span style="font-size: medium;">when set and get &nbsp;json in localStorage will add this type&nbsp;</span></p>
<p>&nbsp;</p>
<p><span style="color: #0000ff;"><span class="s1" style="font-size: medium;">var</span><span style="font-size: medium;"> authToken = JSON.parse(localStorage.getItem(</span><span class="s2" style="font-size: medium;">"authenticationToken"</span><span style="font-size: medium;">));</span></span></p>
<p class="p1">&nbsp;</p>
<p class="p1"><span style="font-size: medium; color: #0000ff;">localStorage.setItem(<span class="s1">"authenticationToken"</span>,JSON.stringify( token));</span></p>
