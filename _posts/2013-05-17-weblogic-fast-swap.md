---
layout: post
title: "Weblogic  fast-swap"
comments: true
---
<p><span style="font-size: small;">This is something that could eat up time in any bigger project. If you make changes to your working application and you need to track down bugs, it's inevitable to redeploy your application on any change. What is done in seconds, if you</span><br /><span style="font-size: small;">a) know the WLS administration and/or</span><br /><span style="font-size: small;">b) your application is quite lean</span><br /><br /><span style="font-size: small;">If you have a fullblown JEE application with all the magic inside, it's no problem to wait for a successful redeployment for minutes.</span><br /><span style="font-size: small;">In practice there are some ways to get rid of this overhead very quickly.</span><br /><br /><span style="font-size: small;">1) Weblogic's ChangeAwareClassLoader (WLS &lt;=10.x)</span><br /><span style="font-size: small;">Java classloaders do not have any standard mechanism to undeploy or unload a set of classes, nor can they load new versions of classes. In order to make updates to classes in a running virtual machine, the classloader that loaded the changed classes must be replaced with a new classloader. When a classloader is replaced, all classes that were loaded from that classloader (or any classloaders that are offspring of that classloader) must be reloaded. Any instances of these classes must be re-instantiated. If you deploy an exploded application and run the WLS in development mode, you can take advantage from the ChangeAwareClassloader. If you make changes to a single class, the WLS simply replaces the whole classloader and starts over with your newly created class. This was one of the first approaches to quicker development roundtrips. Anyway it is still not the solution for bigger applications.</span><br /><br /><span style="font-size: small;">2) Weblogic Fast-Swap (WLS &gt;=10.x)</span><br /><span style="font-size: small;">Java EE 5 introduces the ability to redefine a class at runtime without dropping its ClassLoader or abandoning existing instances. This allows containers to reload altered classes without disturbing running applications, vastly speeding up iterative development cycles and improving the overall development and testing experiences. The usefulness of the Java EE dynamic class redefinition is severely curtailed, however, by the restriction that the shape of the class &ndash; its declared fields and methods &ndash; cannot change. The purpose of FastSwap is to remove this restriction in WLS, allowing the dynamic redefinition of classes with new shapes to facilitate iterative development.</span><br /><br /><span style="font-size: small;">With FastSwap, Java classes are redefined in-place without reloading the ClassLoader, thereby having the decided advantage of fast turnaround times. This means that you do not have to wait for an application to redeploy and then navigate back to wherever you were in the Web page flow. Instead, you can make your changes, auto compile, and then see the effects immediately. </span><br />&nbsp;</p>
<ul>
<ul>
<li><span style="font-size: small;">FastSwap is only supported when WLS is running in development mode. It is automatically disabled in production mode.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Only changes to class files in exploded directories are supported. Modifications to class files in archived applications, as well as archived JAR files appearing in the application&rsquo;s classpath are not supported.</span></li>
</ul>
</ul>
<p><br /><span style="font-size: small;">To enable FastSwap in your application, add &lt;fast-swap&gt;true&lt;/fast-swap&gt; to the weblogic-application.xml file.</span><br /><br /><span style="font-size: small;">FastSwap can also be enabled for a standalone web-application by adding the &lt;fast-swap&gt; element to the weblogic.xml file.</span><br /><br /><span style="font-size: small;">Once FastSwap is enabled at the descriptor level, an appropriate ClassLoader is instantiated when the application is deployed to WLS. It is recommended that you have your IDE setting set to "compile-on-save" so that java files are compiled on saving. The FastSwap agent tries to find all classes that have been modified since the last iteration by looking at all directories in the classpath.</span><br /><br /><span style="font-size: small;">FastSwap is supported with POJOs (JARs), Web applications (WARs) and enterprise applications (EARs) deployed in an exploded format. FastSwap is not supported with resource adapters (RARs).</span><br /><br /></p>
<p>&nbsp;</p>
<dl>Supported changes:</dl>
<ul>
<ul>
<li><span style="font-size: small;">Addition and Removal of static methods</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition and Removal of instance methods</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Changes to static and instance method bodies</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition and Removal of static fields</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition and Removal of instance fields</span></li>
</ul>
</ul>
<dl>limitations:</dl>
<ul>
<ul>
<li><span style="font-size: small;">Java Reflection results do not include newly added fields and methods and include removed fields and methods. As a result, use of the reflection API on the modified classes can result in undesired behavior.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Changing the hierarchy of an already existing class is not supported by FastSwap. For example, either a) changing the list of implemented interfaces of a class; or b) changing the superclass of a class, is not supported.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition or removal of Java annotations is not supported by FastSwap, since this is tied to the reflection changes mentioned above.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition or removal of methods on EJB Interfaces is not supported by FastSwap since an EJB Compilation step is required to reflect the changes at runtime.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition or removal of constants from Enums is not supported.</span></li>
</ul>
</ul>
<ul>
<ul>
<li><span style="font-size: small;">Addition or removal of the finalize method is not supported.</span></li>
</ul>
</ul>
<p><br /><span style="font-size: small;">When FastSwap is enabled, after you recompile a class, FastSwap attempts to redefine classes in existing classloaders. If redefinition fails because your changes fall outside the scope of supported FastSwap changes, the JVM throws an UnsupportedOperationException in the WLS window and in the server log file. Your application will not reflect the changes, but will continue to run. </span></p>
<p><span style="font-size: small;">ref:http://blog.eisele.net<br /></span></p>
