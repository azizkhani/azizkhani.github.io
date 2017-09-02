---
layout: post
title: "docker save vs export "
comments: true
---
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;">Export</span></p>
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;"> is used to persist a container (not an image).container in&nbsp;</span><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;">A running instance of an image is called&nbsp;</span><em style="margin: 0px; padding: 0px; outline: 0px; border: 0px; vertical-align: baseline; font-size: 15px; font-family: Georgia, 'Times New Roman', Times, serif; line-height: 22.5px;">container.</em></p>
<p><span><span style="line-height: 15px; white-space: pre;"><strong>docker export &lt;CONTAINER ID&gt; &gt; /home/export.tar</strong></span></span></p>
<p>for example docker export nginx &gt;/azizkhani/nginx.tar</p>
<p>&nbsp;</p>
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;">Save </span></p>
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;">is used to persist an image (not a container). So we need the image name which</span></p>
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif; font-size: 15px; line-height: 22.5px;"><br /></span></p>
<p><span style="font-family: Georgia, 'Times New Roman', Times, serif;"><span style="font-size: 15px; line-height: 22.5px;">docker save nginx &gt; /azizkhani/nginx.tar</span></span></p>
