---
layout: post
title: "Hibernate: Version-Based Optimistic Concurrency Control"
comments: true
---
<p><span style="font-size: small;">Optimistic locking discards all incoming changes that are relative to an older entity version. But everything has a cost and optimistic locking makes no difference.</span></p>
<p><span style="font-size: small;">The optimistic concurrency control mechanism takes an all-or-nothing approach even for non-overlapping changes. If two concurrent transactions are changing distinct entity property subsets then there&rsquo;s no risk of losing updates.</span></p>
<p><span style="font-size: small;">Two concurrent updates, starting from the same entity version are always going to collide. It&rsquo;s only the first update that&rsquo;s going to succeed, the second one failing with an optimistic locking exception. This strict policy acts as if all changes are overlapping. For highly concurrent write scenarios, this single-version check strategy can lead to a large number of roll-backed updates.</span></p>
<p><img class="aligncenter size-full wp-image-32841" style="display: block; margin-left: auto; margin-right: auto;" src="http://a3ab771892fd198a96736e50.javacodegeeks.netdna-cdn.com/wp-content/uploads/2014/11/optimisticlockingoneproductentityoneversion.png" alt="optimisticlockingoneproductentityoneversion" width="509" height="470" /></p>
<p>&nbsp;</p>
<p><img class="decoded" style="display: block; margin-left: auto; margin-right: auto;" src="http://a3ab771892fd198a96736e50.javacodegeeks.netdna-cdn.com/wp-content/uploads/2014/11/optimisticlockingonerootentityoneversion1.png" alt="http://a3ab771892fd198a96736e50.javacodegeeks.netdna-cdn.com/wp-content/uploads/2014/11/optimisticlockingonerootentityoneversion1.png" width="712" height="479" /></p>
