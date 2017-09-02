---
layout: post
title: "WEBLOGIC BEA-002616: Failed to listen on channel on listenAddress:port"
comments: true
---
<p style="margin: 0cm 0cm 0pt; mso-line-height-alt: 13.0pt;"><span style="font-size: 14pt;"><strong><span style="color: #365f91;"><span style="font-family: Cambria;">Technology, KeyWords:</span></span></strong></span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">WebLogic Server 10.3, <span style="mso-bidi-font-weight: bold;">Cluster, Exception;</span> Too many open files, Socket, Linux, SLES</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;"><span style="mso-bidi-font-weight: bold;">Error Message: </span>&lt;BEA-002616&gt; &lt;Failed to listen on channel "Default"&hellip;&gt;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="mso-bidi-font-weight: bold;"><span style="font-size: small;">&nbsp;</span></span></p>
<p style="margin: 0cm 0cm 0pt; mso-line-height-alt: 13.0pt;"><span style="font-size: 14pt;"><strong><span style="font-family: Cambria; color: #365f91;">Problem</span></strong></span><span style="font-size: small;">:</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&lt;Critical&gt; &lt;Server&gt; &lt;BEA-002616&gt; &lt;Failed to listen on channel "Default" on IP_NR:Port, failure count: 1, failing for 0 seconds, java.net.SocketException: Too many open files&gt;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="margin: 0cm 0cm 0pt; mso-line-height-alt: 13.0pt;"><span style="font-size: 14pt;"><strong><span style="color: #365f91;"><span style="font-family: Cambria;">Description </span></span></strong></span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="mso-bidi-font-weight: bold;"><span style="font-size: small;">Weblogic declaration from: </span></span><a href="http://docs.oracle.com/cd/E23549_01/apirefs.1111/e14397/Server.html" target="_blank"><span style="color: #0000ff; font-size: small;">http://docs.oracle.com/cd/E23549_01/apirefs.1111/e14397/Server.html</span></a></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">BEA-002616 </span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">Critical: Failed to listen on channel "channel" on listenAddress:port, failure count: fails1, failing for secs2 seconds, e3</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><strong><span style="font-size: small;">Description </span></strong></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">The server listener will retry the listen after a short delay.</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><strong><span style="font-size: small;">Cause </span></strong></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">The server got an exception while trying to accept client connections. It will try to backoff to aid recovery.</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><strong><span style="font-size: small;">Action </span></strong></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">The OS limit for the number of open file descriptor (FD limit) needs to be increased. Tune OS parameters that might help the server to accept more client connections (e.g. TCP accept back log).</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="margin: 0cm 0cm 0pt; mso-line-height-alt: 13.0pt;"><span style="font-size: 14pt;"><strong><span style="color: #365f91;"><span style="font-family: Cambria;">More detail and Background information: </span></span></strong></span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&ldquo;Tune OS parameters&rdquo; depends on OS which you use. For Linux, kernel parameters need adjustment- exact details depend on the distribution. There are individual user limits for open files. You can use `<em><span style="text-decoration: underline;">ulimit -a</span></em>` command to find out the Linux for the user that owns.</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">You can find information regarding the important parameters e.g. number of "open files" or similar entry. Please consider, in AIX, the user limits apply as well as a system OS configuration for the total number of open files allowed on the host.</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="margin: 0cm 0cm 0pt; mso-line-height-alt: 13.0pt;"><span style="font-size: 14pt;"><strong><span style="color: #365f91;"><span style="font-family: Cambria;">Solution</span></span></strong></span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">Here is an example how can you check and isolate the position of error. </span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; text-indent: -18pt; margin: 0cm 0cm 0pt 36pt; mso-list: l0 level1 lfo1;"><span style="mso-fareast-font-family: Arial; mso-bidi-font-family: Arial;"><span style="mso-list: Ignore;"><span style="font-size: small;">1-</span><span style="font: 7pt 'Times New Roman';">&nbsp;&nbsp;&nbsp; </span></span></span><span style="font-size: small;">Check linux configuration (e.g. on host XXX):</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&gt; ulimit &ndash;a</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">core file size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(blocks, -c) 1</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">data seg size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(kbytes, -d) unlimited</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">scheduling priority<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-e) 0</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">file size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(blocks, -f) unlimited</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">pending signals<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-i) 127575</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">max locked memory<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(kbytes, -l) 64</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">max memory size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(kbytes, -m) 13887980</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;"><span style="background: lime; mso-highlight: lime;">open files<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-n) 65600</span> <span style="font-family: Wingdings; mso-ascii-font-family: Arial; mso-hansi-font-family: Arial; mso-char-type: symbol; mso-symbol-font-family: Wingdings; mso-no-proof: yes;"><span style="mso-char-type: symbol; mso-symbol-font-family: Wingdings;">&agrave;</span></span> OK</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">pipe size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(512 bytes, -p) 8</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">POSIX message queues<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp; </span>(bytes, -q) 819200</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">real-time priority<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-r) 0</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">stack size<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(kbytes, -s) 8192</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">cpu time<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(seconds, -t) unlimited</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">max user processes<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-u) 127575</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">virtual memory<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(kbytes, -v) 17749200</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">file locks<span style="mso-spacerun: yes;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span>(-x) unlimited</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">The open file descriptor limit is at 65600 as recommended by Oracle. </span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; text-indent: -18pt; margin: 0cm 0cm 0pt 36pt; mso-list: l0 level1 lfo1;"><span style="mso-fareast-font-family: Arial; mso-bidi-font-family: Arial;"><span style="mso-list: Ignore;"><span style="font-size: small;">2-</span><span style="font: 7pt 'Times New Roman';">&nbsp;&nbsp;&nbsp; </span></span></span><span style="font-size: small;">Check currently open files</span></p>
<p style="line-height: 13pt; text-indent: -18pt; margin: 0cm 0cm 0pt 72pt; mso-list: l0 level2 lfo1; mso-add-space: auto;"><span style="mso-fareast-font-family: Arial; mso-bidi-font-family: Arial;"><span style="mso-list: Ignore;"><span style="font-size: small;">a.</span><span style="font: 7pt 'Times New Roman';">&nbsp;&nbsp;&nbsp; </span></span></span><span style="font-size: small;">Find PID of Managed Server</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&gt; ps -fea|grep myManagedServer</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; text-indent: -18pt; margin: 0cm 0cm 0pt 72pt; mso-list: l0 level2 lfo1; mso-add-space: auto;"><span style="mso-fareast-font-family: Arial; mso-bidi-font-family: Arial;"><span style="mso-list: Ignore;"><span style="font-size: small;">b.</span><span style="font: 7pt 'Times New Roman';">&nbsp;&nbsp;&nbsp; </span></span></span><span style="font-size: small;">Check open files</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">Please use lsof (list open files) that lists information about files opened by processes</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">You see list of open files via (e.g.PID is here 1234)</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&gt;lsof -p 1234 <span style="mso-spacerun: yes;">&nbsp;</span></span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">In order to findour the number of open files:</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&gt; lsof -p 1234 | wc &ndash;l</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">&nbsp;</span></p>
<p style="line-height: 13pt; margin: 0cm 0cm 0pt;"><span style="font-size: small;">In this case, we observed that application has 13 thousand connections on "CLOSE_WAIT" status. This usually happens when the application doesn't close the connections properly:</span></p>
