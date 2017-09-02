---
layout: post
title: "Programming Like Kent Beck "
comments: true
---
<p class="date">Posted by <a href="http://theholyjava.wordpress.com">Jakub Hol&yacute;</a> on September 12, 2012</p>
<p><em>Republished from <a href="http://blog.iterate.no/2012/06/20/programming-like-kent-beck/">blog.iterate.no</a> with the permission of my co-authors Stig Bergestad and Krzysztof Grodzicki.</em></p>
<p>Three of us, namely Stig, Krzysztof, and Jakub, have had the pleasure of spending a week with Kent Beck during Iterate Code Camp 2012, working together on a project and learning programming best practices. We would like to share the valuable lessons that we have learnt and that made us better programmers (or so we would like to think at least).</p>
<p>&nbsp;</p>
<h2>Values Underlying the Programming Style</h2>
<p>Most of the things that we have learnt stem from three basic values: communication, simplicity, and flexibility (in the order of importance). We will introduce them briefly here, you can find a more detailed description in Kent&rsquo;s book <a href="http://www.amazon.com/Implementation-Patterns-Kent-Beck/dp/0321413091/">Implementation Patterns</a>, along with few fundamental practices such as the application of symmetry.</p>
<h3>Communication</h3>
<p>Programs are read much more often than written and therefore should communicate clearly their intent. Code is primarily means of communication. (For a typical enterprise system, a lot of code will be modified by many programmers over 5 &ndash; 15 years and they&rsquo;ll all need to understand it.)</p>
<h3>Simplicity</h3>
<p>Eliminate excess complexity. Apply simplicity at all levels. Simplicity helps communication by making programs easier to understand. Communication helps simplicity by making it easier to see what is excess complexity.</p>
<h3>Flexibility</h3>
<p>&ldquo;Making workable decisions today and maintaining the flexibility to change your mind in the future is a key to good software development.&rdquo; &mdash; Implementation Patterns, Kent Beck</p>
<p>Programs should be flexible in the ways they change, they should make common changes easy or at least easier. Complexity can often arise from excess flexibility, but if that flexibility is not needed then it is waste. The best kind of flexibility comes from simplicity coupled with extensive tests. Trying to create flexibility through design phases or the likes usually ends up with this kind of &ldquo;complex flexibility&rdquo;. Most of the time you do not have enough information to make a proper design decision about where your program will need to change, so the lean mantra of <a href="http://www.codinghorror.com/blog/2006/10/the-last-responsible-moment.html">postponing your decisions til the last responsible moment</a> is a valid and useful approach. That is when you have the best grounds for any decision.</p>
<h3>Summary</h3>
<p>Write code that communicates well what and why is done so that your co-workers and future maintainers can take it over without too much cost. (Yet you have to assume some level of skill and knowledge in you audience.) You cannot foresee the future so keep your code simple and sufficiently flexible so that it can evolve.</p>
<h2>Key Learnings</h2>
<h3>1. You Ain&rsquo;t Gonna Need It!</h3>
<blockquote>
<p>What is today&rsquo;s demo? What test to start with?</p>
</blockquote>
<p>Before we arrived, we settled on a topic that we thought would be fun and challenging. We settled on trying our hands at prototyping a highly scalable, distributed database. We expected upon arrival to spend few hours discussing approaches to how we should actually implement this. After all, there are lot of things to consider: replication strategies, consistent hashing, cluster membership auto-discovery, and conflict resolution, to name a few. If you have just 5 days, you need to plan how to implement it in the simplest possible way. What to do. What to skip. Right? Wrong. Instead of any planning, Kent just asked us what would be the demo we would like to show at the end of the day. And his next question was what test to write.</p>
<p>It turned out to be a very smart approach because we actually implemented only a very small subset of the possible functionality, deciding daily what to do next based on our experiences with the problem so far. Any discussion from the beginning longer than 10 minutes would be 90% wasted time. This doesn&rsquo;t mean that planning is bad (though <a href="http://livebyquotes.com/2012/in-preparing-for-battle-i-have-always-found-that-plans-are-useless-but-planning-is-indispensable-gen-dwight-eisenhower/">the resulting plans are usually useless</a>), it only means that we usually do much more of it than we actually need. Getting real feedback and basing our decisions on that, on real data, is much more practical and valuable than any speculations.</p>
<p>Therefore prefer on-going planning based on feedback and experience to extensive up-front planning. Ask yourself: What am I going to present at the next demo/meeting/day? What test to write to reflect that and thus guide my development effort?</p>
<h3>2. Write High-Level Tests to Guide the Development</h3>
<p>The goal of our second day was replication, demonstrated by writing to one instance, killing it, and reading the (replicated) data from the second instance. We started by writing a <a href="https://github.com/iterate/codecamp2012/blob/369bfddad85ecb26322d64ee0d7db7bc5c129b5e/src/test/java/no/iterate/graft/GraftReplicationTest.java">corresponding test</a>, which follows these steps closely, nearly literally:</p>
<div id="highlighter_149892" class="syntaxhighlighter  ">
<div class="lines">
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>1</code></td>
<td class="content"><code class="plain">List&amp;lt;Graft&amp;gt; grafts = Graft.getTwoGrafts();</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>2</code></td>
<td class="content"><code class="plain">Graft first = grafts.get(</code><code class="value">0</code><code class="plain">);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>3</code></td>
<td class="content"><code class="plain">Graft second = grafts.get(</code><code class="value">1</code><code class="plain">);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>4</code></td>
<td class="content">&nbsp;</td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>5</code></td>
<td class="content"><code class="plain">first.createNode().put(&amp;quot;key&amp;quot;, &amp;quot;value&amp;quot;)</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>6</code></td>
<td class="content"><code class="plain">first.kill();</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>7</code></td>
<td class="content">&nbsp;</td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>8</code></td>
<td class="content"><code class="plain">assertNotNull(second.getNodeByProperty(&amp;quot;key&amp;quot;, &amp;quot;value&amp;quot;));</code></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
<p>(The API of course evolved later into something more general.)</p>
<p>Now the interesting thing is that this is not a unit test. It is basically an integration test, or to use a less technical term, a story test exercising a rather high-level feature. A feature of interest to the customer. While a unit tests tells me &ldquo;this <em>class</em> is working as intended,&rdquo; a story test tells me &ldquo;this <em>feature</em> works as intended&rdquo;.</p>
<p>I used to think about TDD at the unit/class level but this is TDD at a much higher level. It has some interesting properties:</p>
<ul>
<li>It helps measure real progress of the project because it exercises something that is actually meaningful to the customer (if you permit me to use this &ldquo;customer&rdquo; in a little blurry fashion)</li>
<li>It helps keep you focused on delivering business functionality (by being on its level)</li>
<li>It&rsquo;s likely to stay mostly unchanged and live much longer than unit tests or actually most of the code base because it is on such a conceptual level</li>
</ul>
<p>Now, according to the <a href="http://www.ibm.com/developerworks/java/library/j-aopwork11/TestingPyramid.jpg">testing pyramid</a>, there are of course fewer story tests than there are unit tests, and story tests do not test all possible cases. Does it mean that you need to do all these story tests and then do them again only in smaller unit tests? No, that is not the point. Getting back to the principle of flexibility and the way things change, create additional unit tests only when you need them. For example when you encounter some case where the first story test did not actually &ldquo;capture the whole&rdquo; properly, or when you discover a really important corner case, or when you want to focus on implementing a part of the overall solution. Speculating about failure points can be just as wasteful as speculating about design.</p>
<h3>3. Best Practices for [Unit] Testing</h3>
<h4>Write Tests From the End</h4>
<p>We normally start a test with an idea of what we want to verify, but we may be not completely sure how to arrive there. Therefore it is good practice to express what we do know, the desired end-result, first. We do this in the form of an assertion and only then shift our focus to figuring how to get there. That&rsquo;s how we started the test of replication in Graft, shown above.</p>
<p>This is an application of the key principle of focus.</p>
<h4>Write Implementation in Tests, Refactor Later</h4>
<p>You know the functionality you want and so you start writing the test for it. Instead of thinking about how it should be organized (what classes to create, where to put them, whether to use a factory class or a factory method), why not initially write the code directly in the test method? You can always factor out the code later. This way you can focus on what&rsquo;s really important &ndash; describing the desired functionality with a test &ndash; instead of being distracted by secondary considerations. Additionally, by postponing the decision about the internal organization of the implementation, you will have more knowledge when actually deciding it and you will likely end up with a better solution.</p>
<p>Key principles: Focus, avoiding premature decision-making.</p>
<h4>Bottom-up Design</h4>
<p>Avoids:</p>
<ul>
<li>assuming too much, too early</li>
<li>locking yourself into a specific design and premature design</li>
<li>restricting yourself (you will usually end up with the design you first intended)</li>
</ul>
<p>Start by implementing small parts of functionality. Then combine them to form more complex behavior. Don&rsquo;t get distracted by dependencies, write simple stubs for them that you will replace later with real implementations. Using this technique you are not bound to design decisions taken at the beginning as in the &lsquo;top-down&rsquo; approach. It requires a little bit of intuition and some experience, but combined with TDD it helps to make better design and implementation.</p>
<p>We found this technique quite useful as we didn&rsquo;t know the final solution at the beginning. When developing Graft, we haven&rsquo;t designed the whole application up-front. We picked a use case on the first day, implemented it, and continued by choosing and implementing other use cases each day.</p>
<h4>Act &amp; Assert at the Same Level of Abstraction</h4>
<p>Our Graft DB has a telnet-like interface for receiving commands from users. Consider the following two (simplified) variations of the <a href="https://github.com/iterate/codecamp2012/blob/2889f05057c4d339b6065a7e81f1d95de3456017/src/test/java/no/iterate/geekolympics/remote/CommandProcessorTest.java#L22">addComment test</a>:</p>
<div id="highlighter_466476" class="syntaxhighlighter  ">
<div class="lines">
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>1</code></td>
<td class="content"><code class="comments">// Test 1</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>2</code></td>
<td class="content"><code class="plain">Graft db = ...; </code><code class="keyword">this</code><code class="plain">.subject = </code><code class="keyword">new</code> <code class="plain">CommandProcessor(db);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>3</code></td>
<td class="content"><code class="plain">subject.process(&amp;quot;addComment eventId my_comment&amp;quot;);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>4</code></td>
<td class="content">&nbsp;</td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1 highlighted">
<table>
<tbody>
<tr>
<td class="number"><code>5</code></td>
<td class="content"><code class="plain">assertThat(subject.process(&amp;quot;getComments eventId&amp;quot;)).isEqualTo(&amp;quot;my_comment&amp;quot;);</code></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
<p>&nbsp;</p>
<div id="highlighter_751387" class="syntaxhighlighter  ">
<div class="lines">
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>1</code></td>
<td class="content"><code class="comments">// Test 2 (same setUp)</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>2</code></td>
<td class="content"><code class="plain">subject.process(&amp;quot;addComment eventId my_comment&amp;quot;);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>3</code></td>
<td class="content">&nbsp;</td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2 highlighted">
<table>
<tbody>
<tr>
<td class="number"><code>4</code></td>
<td class="content"><code class="plain">assertThat(db.getComments(&amp;quot;eventId&amp;quot;)).containsOnly(&amp;quot;my_comment&amp;quot;);</code></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
<p>The first test, while testing the addComment command, uses another command &ndash; getComments &ndash; to check the resulting state. It uses only a single API entry point &ndash; <em>subject</em> &ndash; during the whole test. The second test accesses directly the underlying database instance and its API to get the same data, i.e. aside of <em>subject</em> it uses also the underlying <em>db</em>.</p>
<p>Thus the first test is not truly &ldquo;unit&rdquo; test as it depends on the correctness of another method of the tested class. The second test is much more focused and potentially simpler to write as it accesses directly the target data structure and thus performs the checks right at the source.</p>
<p>We would argue that tests like the first one, which perform all operations at the same level, namely the level of the public API of the object under test, are better. &ldquo;Better&rdquo; here means easier to understand and, more importantly, much more stable and maintainable because they are not coupled to the internal implementation of the functionality being tested. The price of increased complexity of these unit-integration tests (due to relying on multiple methods in each test) is absolutely worth the gain.</p>
<p>Tests similar to the second one are none the less more common, either accessing directly the underlying layers (an object, property, database, &hellip;) or using mocks to gain the possibility of direct verification of side-effects. These techniques often lead to coupled and hard to maintain tests and should be limited to the &ldquo;private unit tests,&rdquo; as described and argued in <a href="http://theholyjava.wordpress.com/2011/10/20/never-mix-public-and-private-unit-tests/">Never Mix Public and Private Unit Tests!</a></p>
<h3>4. Focus!</h3>
<ul>
<li>Put tasks that pop up on a Later list instead of doing them at once</li>
<li>Focus on fixing the test first &ndash; however ugly and simple (and refactor later)</li>
<li>Focus on the current needs &ndash; no premature abstraction</li>
</ul>
<p>One thing that really caught our attention is Kent&rsquo;s focus on what he is doing at any moment. Being focused means concentrating on finishing that one thing you&rsquo;re currently doing without getting distracted by other concerns, however important or simple to fix. (Side note: Never say never.) When having a failing test, focus on making it pass quickly, no matter how ugly the (temporary) solution is or that it &ldquo;cuts corners.&rdquo; If you notice along the way something else that needs to be done &ndash; giving a method a better name, removing a dead code, fixing an unrelated bug &ndash; don&rsquo;t do it, put it on a task list and do it later. Otherwise you risk losing your attention and the current context. Do one thing at a time. When making a test pass, focus just on that, and leave concerns such as good code til the subsequent refactoring (which should follow shortly). (This reminds me of the <a href="http://mikadomethod.wordpress.com/2009/12/09/introduction-to-the-mikado-method/">Mikado method</a> for large-scale refactorings, whose main purpose is also to keep focus and not getting lost in many sidetracks.)</p>
<p>A related practice is to focus on the current needs when implementing a feature, without speculatively designing for tomorrow&rsquo;s needs (possibly literally tomorrow). Focus on what is needed right now, to finish the current task, and make the solution simple so that it will be easy to refactor and extend for both known and unforseen future needs. As Kent argues in Implementation Patterns (and others elsewhere), we&rsquo;re very bad at speculative design, i.e. the future needs are usually quite different from what we expected and therefore it&rsquo;s better to create solutions that are simple and with that also flexible. You of course need to pay some attention to the future needs but far less than we tend to do. Admit to yourself that you cannot predict the future. Even if you know what else is going to be required, how can you know that no new requirements that would change or delay that (up til infinity) will appear?</p>
<h2>Some other stuff we learned</h2>
<h3>Parallel Design</h3>
<p dir="ltr">Parallel design means that when changing a design, you keep the old design as long as possible while gradually adding the new one and then you gradually switching to the new design. This applies both at large and also (surprisingly) small scale. Though it&rsquo;s costly &ndash; you have to figure out how to have them both run and it requires more effort to have them both &ndash; it often pays off because it&rsquo;s safer and it enables resumable refactoring, discussed below.</p>
<p dir="ltr">An example of a high-level parallel design is the replacement of a RDBMS with a NoSQL database. You&rsquo;d start by implementing the code for writing into the new DB, then you would use it and write both to the old and the new one, then you would start also reading from the new one (perhaps comparing the results to the old code to verify their correctness) while still using the old DB&rsquo;s data. Next you would start actually using the NoSQL DB&rsquo;s data, while still writing to/reading from the old DB (so that you could easily switch back). Only when the new DB proves itself would you gradually remove the old DB.</p>
<p dir="ltr">An example of a micro-level parallel design is the replacement of method parameters (message etc.) with the object they come from (an Edge), as <a href="https://github.com/iterate/codecamp2012/commit/cc04f0bb60d8260456049790793d462ce8810ef2#diff-1">we did for notifyComment</a>:</p>
<div id="highlighter_307072" class="syntaxhighlighter  ">
<div class="lines">
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>1</code></td>
<td class="content"><code class="plain">- public void notifyComment(String message, String eventName, String user) {</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>2</code></td>
<td class="content"><code class="plain">-&nbsp;&nbsp;&nbsp; notifications.add(user + &amp;quot;: commented on &amp;quot; + eventName + &amp;quot; &amp;quot; + message);</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>3</code></td>
<td class="content"><code class="plain">---</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt2">
<table>
<tbody>
<tr>
<td class="number"><code>4</code></td>
<td class="content"><code class="plain">+ public void notifyComment(Edge target) {</code></td>
</tr>
</tbody>
</table>
</div>
<div class="line alt1">
<table>
<tbody>
<tr>
<td class="number"><code>5</code></td>
<td class="content"><code class="plain">+&nbsp;&nbsp;&nbsp; notifications.add(target.getTo().getId() + &amp;quot;: commented on &amp;quot; + target.getFrom().getId() + &amp;quot; &amp;quot; + target.get(&amp;quot;comment&amp;quot;));</code></td>
</tr>
</tbody>
</table>
</div>
</div>
</div>
<p dir="ltr">The steps were:</p>
<ol>
<li>Adding the Edge as another parameter (Refactor &ndash; Change Method Signature)</li>
<li>Replacing one by one usages of the original parameters with properties of the target Edge (Infinitest running tests automatically after each change to verify we&rsquo;re still good)</li>
<li>Finally removing all the original parameters (Refactor &ndash; Change Method Signature)</li>
</ol>
<p>The good thing is that your code always works and you can commit or stop at any time.</p>
<h3>Resumable Refactoring</h3>
<p>If you apply the practices described below when performing a larger-scale refactoring then your code will always be buildable and you will be able to stop in the middle of the refactoring and continue (or not) at any later time.</p>
<p>The practices are parallel design and going forward in <a href="http://theholyjava.wordpress.com/2012/03/12/kent-beck-best-practices-for-software-design-with-low-feature-latency-and-high-throughput/">small, safe steps</a> i.e. steps that provably do not break anything. In essence it&rsquo;s about keeping the oversight and control, at each step you know exactly what you did which broke the test and this way you can not only quickly put the application back in a working state, but also quickly hone in on what exactly caused the problem.</p>
<p>(The Mikado method mentioned above is a great guide for refactoring systems where every change reveals a number of other changes required to make it possible. Of course the ultimate resource for refactoring legacy systems is Michael Feathers&rsquo;s <a href="http://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052/">Working Effectively with Legacy Code</a>).</p>
<h3>Refactor on Green, at Will</h3>
<p dir="ltr">The dogmatic TDD practitioners claim that you cannot change the behavior of production code unless some test forces you to do so. Thus it might be refreshing to hear that Kent doesn&rsquo;t hesitate to <a href="http://cleancoder.posterous.com/the-transformation-priority-premise">generalize the code</a> (e.g. by replacing fakes with a real implementation) even though there are no tests that require the generalization to pass.</p>
<p dir="ltr">On the other hand it doesn&rsquo;t mean that forcing a generalization by tests is a bad thing or that you should not do it. This is basically a question of the economics of software development, of balancing the cost (of writing and maintaining tests) with the benefits (defect and regression prevention). It&rsquo;s a question of the risk involved and of your confidence in your coding skills. Kent has rightfully much more confidence in his coding skills (and much more experience with it) than many of us. Our confidence is quite low based on past experiences and therefore we&rsquo;ll probably go on enforcing generalizations with tests.</p>
<p dir="ltr">We&rsquo;d close this topic by quoting Kent speaking about <a href="http://stackoverflow.com/a/153565">how much testing to do</a>:</p>
<blockquote>
<p>I get paid for code that works, not for tests, so my philosophy is to test as little as possible to reach a given level of confidence (I suspect this level of confidence is high compared to industry standards, but that could just be hubris). If I don&rsquo;t typically make a kind of mistake (like setting the wrong variables in a constructor), I don&rsquo;t test for it. I do tend to make sense of test errors, so I&rsquo;m extra careful when I have logic with complicated conditionals. When coding on a team, I modify my strategy to carefully test code that we, collectively, tend to get wrong.</p>
<p>Different people will have different testing strategies based on this philosophy, but that seems reasonable to me given the immature state of understanding of how tests can best fit into the inner loop of coding. Ten or twenty years from now we&rsquo;ll likely have a more universal theory of which tests to write, which tests not to write, and how to tell the difference. In the meantime, experimentation seems in order.</p>
</blockquote>
<h3>Symmetry in the Code</h3>
<p>Symmetry is an abstract concept, more specific than the values of communication, simplicity, and flexibility, but still rather general. In Implementation Patterns Kent refers to symmetry as a programming principle.</p>
<p>Code with symmetries is easier to grasp than code that is asymmetric. It&rsquo;s easier to read and understand. So what, more specifically, is symmetric code? To quote Kent again:</p>
<blockquote>
<p>Symmetry in code is where the same idea is expressed the same way everywhere it appears in the code.</p>
</blockquote>
<p>Imagine a code where the some idea, like &ldquo;getting the last updated document from the DB,&rdquo; is implemented several times. The code is asymmetric if the method names differ, if they do things in different order, if there are some important differences between them. When you ask yourself &ldquo;what does this method do&rdquo; and you arrive at pretty much the same answer for all methods in spite of all the differences, then you have some violation of symmetry. An example of symmetry in code is keeping the abstraction level consistent within a code block, like a method. if the block is a mix of low level assignments and method calls, you may want to see if you can abstract away the assignments with a method. The astute reader have probably noticed that consistency is a large part of symmetry: being consistent with abstraction levels, consistent with method naming, and so on. But symmetry is more abstract in that it deals more with ideas, not rules (such as the rule that class and method names should be in camel-case).</p>
<h3>And What Do you Know, Even Some More &hellip;</h3>
<ul>
<li><strong>Manage your energy</strong> &ndash; be aware of your energy and stop before becoming tired. Don&rsquo;t forget to take breaks. A rested developer is multiple times more productive than a tired one. (J.B. Rainsberger in <a href="http://www.youtube.com/watch?v=7HecgbghFTk">The Economics of Software Design</a> shares the story of working so intensively that he became exhausted and totally unproductive).</li>
<li><strong>Pair-programming is a <a href="http://arlobelshee.com/post/is-pair-programming-for-me">skill one must consciously learn</a></strong> (and it may be more challenging for some personality types, which shall to be respected)</li>
<li><strong>Prefer IDE&rsquo;s refactorings to manual changes</strong> &ndash; f.ex. none of us had ever before used the &ldquo;inline&rdquo; refactoring while Kent uses it all the time. Once you master the refactorings, they&rsquo;ll become much more efficient than changing things manually and, more importantly, they avoid the small but non-zero probability of breaking something (remember that Murphy guy who said &ndash; what can break will break)</li>
</ul>
<h2>Code</h2>
<p>You can find code for Iterate Code Camp 2012 on GitHub &ndash; <a title="Github codecamp2012" href="https://bit.ly/codecamp2012">bit.ly/codecamp2012</a></p>
<h2>Conclusion</h2>
<p>We hope that you, our dear reader, find some of these ideas interesting and have got inspired to try them in your daily practice, as we did.</p>
<h2>Related Resources</h2>
<ul>
<li>Jakub&rsquo;s blog post <a href="http://theholyjava.wordpress.com/2011/11/21/principles-for-creating-maintainable-and-evolvable-tests/">Principles for Creating Maintainable and Evolvable Tests</a> summarizes some complementary principles for writing tests that he learnt from Kent</li>
<li>Rich Hickey: <a href="http://www.infoq.com/presentations/Simple-Made-Easy">Simple Made Easy</a> &ndash; a great talk that explains the crucial difference between &ldquo;simple&rdquo; (vs. complex) and &ldquo;easy&rdquo; and how our languages and tools aren&rsquo;t as simple as they should be, often because they try to be easy</li>
</ul>
<p style="text-align: center;"><em>- Krzysztof, Stig, and Jakub, June 2012 -</em></p>
