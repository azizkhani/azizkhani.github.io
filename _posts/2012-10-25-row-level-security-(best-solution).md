---
layout: post
title: "ROW LEVEL SECURITY (BEST SOLUTION?)"
comments: true
---
<p>&nbsp;</p>
<p>HELP ME<br /><span style="font-size: small;">here might be special rows in a database which should only visible and accessible by users with special privileges. To avoid unnecessary round-trips, we currently modify the SQL queries to join with our authorization data to get only the visible rows for the current user. </span></p>
<p><span style="font-size: small;">But this concepts doesn't feel 'right' to me, because we <strong>mix business code with security related code</strong> which should be orthogonal and independent from each other.</span></p>
<p>&nbsp;</p>
<ul>
<li><strong>What solutions are available/possible?</strong></li>
<li><strong>How do you implement row-level security</strong> (especially in combination with hibernate)<strong>?</strong></li>
</ul>
<p><span style="font-size: small;">The idea is that you can implement row level functionality in two ways: directly setting restrictions in your repository or binding the restrictions via AOP. The latter is preferred because security layer should be separated from business logic (orthogonal concerns).</span></p>
<p>&nbsp;</p>
<p><span style="font-size: small;">In Hibernate you can use the concept of filters which are applied transparently and repository doesn't know about them. You can add such filters via AOP. The other way is intercepting session.createCriteria() and adding Restrictions to the Criteria transparently using AOP.</span></p>
<p>&nbsp;</p>
