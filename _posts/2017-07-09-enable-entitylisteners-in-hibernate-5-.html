---
layout: post
title: "enable @EntityListeners  in Hibernate 5 "
comments: true
---
<p>I have BaseEntity and i want to set some property in all hibernate add and update ,for do this request we can do that with this code&nbsp;</p>
<p>&nbsp;</p>
<p class="p1">@MappedSuperclass</p>
<p class="p2"><span class="s1">@EntityListeners</span>(BaseEntityListener.<span class="s2">class</span>)</p>
<p class="p2"><span class="s2">public</span> <span class="s2">abstract</span> <span class="s2">class</span> BaseEntity&lt;T&gt; <span class="s2">implements</span> Serializable {</p>
<p class="p3">&nbsp;</p>
<p class="p2"><span class="s2">private</span> <span class="s2">static</span> <span class="s2">final</span> <span class="s2">long</span> <span class="s3">serialVersionUID</span> = 4295229462159851306L;</p>
<p class="p3">&nbsp;</p>
<p class="p1">@Id</p>
<p class="p2"><span class="s1">@GeneratedValue</span>(strategy = GenerationType.<span class="s3">IDENTITY</span>)</p>
<p class="p4">private<span class="s4"> T </span><span class="s3">id</span><span class="s4">;</span></p>
<p class="p3">&nbsp;</p>
<p class="p2"><span class="s1">@Column</span>(name = <span class="s5">"version"</span>)</p>
<p class="p5"><span class="s2">private</span><span style="color: #000000;"> Integer </span><span class="s3">version</span><span style="color: #000000;">;</span></p>
<p class="p3">&nbsp;</p>
<p class="p1">@NotNull</p>
<p class="p2"><span class="s1">@ManyToOne</span>(fetch = FetchType.<span class="s3">LAZY</span>)</p>
<p class="p2"><span class="s1">@JoinColumn</span>(name = <span class="s5">"createdby"</span>, updatable = <span class="s2">false</span>)</p>
<p class="p6"><span class="s2">private</span><span class="s4"> User </span>createdBy<span class="s4">;</span></p>
<p class="p3">&nbsp;</p>
<p class="p1">@NotNull</p>
<p class="p2"><span class="s1">@ManyToOne</span>(fetch = FetchType.<span class="s3">LAZY</span>)</p>
<p class="p1">@JoinColumn<span class="s4">(name = </span><span class="s5">"updatedby"</span><span class="s4">)</span></p>
<p class="p6"><span class="s2">private</span><span class="s4"> User </span>updatedBy<span class="s4">;</span></p>
<p class="p3">&nbsp;</p>
<p class="p2"><span class="s1">@Column</span>(name = <span class="s5">"createddate"</span>, updatable = <span class="s2">false</span>)</p>
<p class="p2"><span class="s2">private</span> Date <span class="s3">createdDate</span> = <span class="s2">new</span> Date();</p>
<p class="p3">&nbsp;</p>
<p class="p7"><span class="s1">@Column</span><span class="s4">(name = </span>"updateddate"<span class="s4">)</span></p>
<p class="p2"><span class="s2">private</span> Date <span class="s3">updatedDate</span> = <span class="s2">new</span> Date();</p>
<p class="p3">&nbsp;</p>
<p class="p2"><span class="s1">@Column</span>(name = <span class="s5">"ip"</span>)</p>
<p class="p2"><span class="s2">private</span> String <span class="s3">ip</span> = <span class="s5">"127.0.0.1"</span>;</p>
<p class="p3">&nbsp;</p>
<p class="p3">&nbsp;</p>
<p class="p2"><span style="color: #931a68;">,..</span></p>
<p>&nbsp;</p>
<p class="p2">}</p>
<p class="p2">&nbsp;</p>
<p class="p1"><span class="s1">public</span> <span class="s1">class</span> BaseEntityListener {</p>
<p class="p2">&nbsp;</p>
<p class="p3">@PrePersist</p>
<p class="p3">@PreUpdate</p>
<p class="p1"><span class="s1">private</span> <span class="s1">void</span> initializeCreatedAt(<span class="s3">BaseEntity</span> <span class="s4">baseEntity</span>) {</p>
<p class="p1">System.<span class="s5">out</span>.println(<span class="s6">"BaseEntityListener"</span>);</p>
<p class="p1"><span class="s4">baseEntity</span>.setIp(SecurityUtility.getRequestedIp());</p>
<p class="p1"><span class="s4">baseEntity</span>.setCreatedBy(SecurityUtility.getAuthenticatedUser());</p>
<p class="p1"><span class="s4">baseEntity</span>.setUpdatedBy(SecurityUtility.getAuthenticatedUser());</p>
<p class="p1"><span class="s4">baseEntity</span>.setCreatedDate(<span class="s1">new</span> Date());</p>
<p class="p1"><span class="s4">baseEntity</span>.setUpdatedDate(<span class="s1">new</span> Date());</p>
<p class="p1">}</p>
<p class="p1">}&nbsp;</p>
<p>in hibernate 5&nbsp;EntityListeners dose not work</p>
