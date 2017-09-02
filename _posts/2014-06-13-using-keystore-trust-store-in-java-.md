---
layout: post
title: "using keystore  & trust store in java "
comments: true
---
<p>&nbsp;</p>
<p><span style="font-size: small; color: #000080;"><span style="color: #000000;">add this code for run application that use&nbsp; keystore</span> <br /></span></p>
<p><span style="font-size: small; color: #000080;"><span style="color: #000000;"><strong>option1</strong></span><br /></span></p>
<p><span style="font-size: small; color: #000080;">System.setProperty("javax.net.ssl.keyStore","/azizkhani/Java/pdf/EIA/keystore.jks");</span><br /><span style="color: #000080;"><span style="font-size: small;">System.setProperty("javax.net.ssl.keyStorePassword", "pass");</span><span style="font-size: small;"><br />System.setProperty("javax.net.debug", "all");</span></span></p>
<p>&nbsp;</p>
<p><strong><span style="color: #000000; font-size: small;">option2</span></strong></p>
<p>&nbsp;</p>
<p><span style="font-size: small; color: #000080;">-Djavax.net.ssl.keyStore=/azizkhani/Java/pdf/EIA/keystore.jks</span></p>
<p><span style="color: #003366;"><span style="font-size: small;">-Djavax.net.ssl.keyStorePassword=pass;</span></span><span style="color: #000080;"><span style="font-size: small;"><br /></span></span></p>
<p>&nbsp;</p>
