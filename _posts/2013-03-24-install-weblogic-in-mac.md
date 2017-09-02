---
layout: post
title: "install weblogic in mac"
comments: true
---
<p>alis-MacBook-Pro:~ aliakbarazizkhani$&nbsp; <strong>cd /System/Library/Frameworks/JavaVM.framework/Versions/1.6.0/Home</strong><br />alis-MacBook-Pro:Home aliakbarazizkhani$ <strong>sudo mkdir -p jre/lib</strong> <br /><br />WARNING: Improper use of the sudo command could lead to data loss<br />or the deletion of important system files. Please double-check your<br />typing when using sudo. Type "man sudo" for more information.<br /><br />To proceed, enter your password, or type Ctrl-C to abort.<br /><br />Password:<br />alis-MacBook-Pro:Home aliakbarazizkhani$ <strong>cd jre/lib</strong><br />alis-MacBook-Pro:lib aliakbarazizkhani$ <strong>sudo touch rt.jar</strong><br />alis-MacBook-Pro:lib aliakbarazizkhani$ <strong>sudo touch core.jar</strong><br />alis-MacBook-Pro:lib aliakbarazizkhani$ <strong>cd /azizkhani/software</strong></p>
<p><strong>java -Dspace.detection=false -Dos.name=unix -XX:MaxPermSize=512m -Xmx1024m -jar wls1035_generic.jar</strong></p>
<p><strong><br /></strong></p>
<p><strong><br /></strong></p>
<p><strong>run</strong></p>
<p><strong><br />export JAVA_HOME=/System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home</strong><br />alis-MacBook-Pro:bin aliakbarazizkhani$ <strong>export MW_HOME=/azizkhani/Oracle/Middlewarea</strong><br />alis-MacBook-Pro:bin aliakbarazizkhani$ <strong>export USER_MEM_ARGS="-Xmx1024m -XX:MaxPermSize=256m"</strong><br />alis-MacBook-Pro:bin aliakbarazizkhani$ <strong>. /azizkhani/Oracle/Middleware/user_projects/domains/base_domain/bin/setDomainEnv.sh</strong><br />alis-MacBook-Pro:base_domain aliakbarazizkhani$<strong> . /azizkhani/Oracle/Middleware/user_projects/domains/base_domain/bin/startWeblogic.sh<br /><br /></strong></p>
