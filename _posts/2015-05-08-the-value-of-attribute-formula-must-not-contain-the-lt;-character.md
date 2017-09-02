---
layout: post
title: "The value of attribute "formula" must not contain the '<' character."
comments: true
---
<p><span style="font-size: small;">hibernate formula dosenot allow user &lt; in select for example i use this formula and get this exception </span></p>
<p><strong><span style="font-size: small;">&nbsp; &lt;property name="debitPrice"&nbsp; not-null="true"&nbsp;&nbsp; formula="(&nbsp; select nvl(sum(d.cost_price),0) from ihs_flat_cost_assign d where d.flat_id=Id&nbsp; and <span style="color: #ff0000;">d.cost_price &lt;=0</span> &nbsp; )&nbsp; "&nbsp;&nbsp; /&gt;</span></strong></p>
<p>&nbsp;</p>
<p><span style="font-size: small;">and i change that to this<br /></span></p>
<p><strong><span style="font-size: small;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &lt;property name="debitPrice"&nbsp; not-null="true"&nbsp;&nbsp; formula="(&nbsp; select nvl(sum(d.cost_price),0) from ihs_flat_cost_assign d where d.flat_id=Id&nbsp; and <span style="color: #ff0000;">0&gt;=d.cost_price</span>&nbsp;&nbsp;&nbsp; )&nbsp; "&nbsp;&nbsp; /&gt;</span></strong></p>
<p><span style="font-size: small;">and problem solve </span></p>
<p><span style="font-size: small;">crazyyyyy bug i dont know whyyyyy</span><br /><br /></p>
