---
layout: post
title: " Hibernate exception _$$_javassist_0 cannot be cast to javassist.util.proxy.Proxy"
comments: true
---
<p><span style="font-size: medium;">hibernate 4.3.7 using javasssist new version and oracle weblogic older than that version for solve this problem will add this configuration to weblogic.xml</span><br /><br /><span style="font-size: medium;">&lt;wls:container-descriptor&gt;</span><br /><span style="font-size: medium;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;wls:prefer-application-packages&gt;</span><br /><span style="font-size: medium;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;wls:package-name&gt;javassist&lt;/wls:package-name&gt;</span><br /><span style="font-size: medium;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;/wls:prefer-application-packages&gt;</span><br /><span style="font-size: medium;">&nbsp;&nbsp;&nbsp; &lt;/wls:container-descriptor&gt;</span></p>
