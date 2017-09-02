---
layout: post
title: " Fluent Object Creation "
comments: true
---
<div>Many posts have been written on this subject (overwhelmingly many) but I just wanted to contribute my two-cents and write a short post about how I use the <em>Fluent Object Creation</em>&nbsp;pattern or object builders in Java to instantiate&nbsp;<em>Value Objects.</em></div>
<p>&nbsp;<em>Value Objects</em>&nbsp;are abstractions that are defined by their state (value) rather than their address in memory. Examples of value objects are things like money, a number, a coordinate, etc. They are used not to describe Business Objects but rather descriptions of concrete indivisible entities. &nbsp;Also, they make great candidates for adding them to collections and maps.</p>
<div><em><br /></em> In Java,&nbsp;<em>Value Objects</em>&nbsp;should be declared final and provide no setter methods, basically making it's state immutable after creation, this is a very important requirement. Declaring them final makes them unable to serve as parent objects. This is done by design since value objects should model small and concrete entities. The reason being is that we should be able to create and compare multiple copies of these objects, which is always done by state not by reference. In addition, you should declare proper <em>equals() </em>and <em>hashCode() </em>methods to qualify for a proper value object.<br /> <br /> In C++, the same principles apply. In C++ you should make use of the <em>Copy Constructor</em>&nbsp;and overload the assignment and comparison operators.&nbsp;&nbsp;<br /> <br /> The&nbsp;<em>Fluent Object Creation</em>&nbsp;pattern makes value object instantiation elegant and clean. There are many benefits that can be gained by using fluent object creation as we will see shortly.&nbsp;</div>
<p>&nbsp;</p>
<div>&nbsp;</div>
<p>&nbsp;</p>
<div>The end result&nbsp;of applying this pattern&nbsp;from the API user's perspective will look like the following:</div>
<p>&nbsp;</p>
<fieldset style="border-color: #ADFF2F; border-style: dashed; font-size: 14px;"><legend></legend><br />
<div style="font-family: Monaco; font-size: 11px;">Money fiveEuros = <span style="color: #941965;">new</span>&nbsp;Money.Builder()</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.currency(Currency<span style="color: #3e38f5;">.EURO</span>)</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.value(5.0L)</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.countryOfOrigin(<span style="color: #3e38f5;">"Spain"</span>)<br /> &nbsp; &nbsp;.type(<span style="color: #3e38f5;">"Coin"</span>)</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.reverse(<span style="color: #3e38f5;">"Map of Europe"</span>)</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.obverse(<span style="color: #3e38f5;">"Map of Spain"</span>)<br /> &nbsp; &nbsp;.addColor(<span style="color: #3e38f5;">"Bronze"</span>)<br /> &nbsp; &nbsp;.addColor(<span style="color: #3e38f5;">"Silver"</span>)</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;.year(<span style="color: #3e38f5;">"1880"</span>)</div>
<div style="font-family: Monaco; font-size: 11px;">.build();</div>
</fieldset>
<p><br /> I think you would agree that this pattern flows a lot more smoother as opposed to this:</p>
<fieldset style="border-color: #adff2f; border-style: dashed; font-size: 14px;"><legend></legend><br />
<div style="font-family: Monaco; font-size: 11px;">Money&nbsp;fiveEuros&nbsp;=&nbsp;<span style="color: #941965;">new</span>&nbsp;Money();</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.setCurrency(Currency<span style="color: #3e38f5;">.EURO</span>);</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.setValue(5.0L);</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.countryOfOrigin(<span style="color: #3e38f5;">"Spain"</span>);</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.type(<span style="color: #3e38f5;">"Coin"</span>);</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.reverse(<span style="color: #3e38f5;">"Map of Europe"</span>);<br /> fiveEuros.obverse(<span style="color: #3e38f5;">"Map of Spain"</span>);</div>
<div style="font-family: Monaco; font-size: 11px;">List&lt;String&gt; colors =&nbsp;<span style="color: #941965;">new</span>&nbsp;ArrayList&lt;String&gt;();</div>
<div style="font-family: Monaco; font-size: 11px;"><span style="color: purple;">for</span>(String color: <span style="color: purple;">new</span> String[] {<span style="color: #3e38f5;">"Bronze",&nbsp;</span><span style="color: #3e38f5;">"Silver"</span>}) {</div>
<div style="font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;colors.add(color);</div>
<div style="font-family: Monaco; font-size: 11px;">}</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.setColors(colors);</div>
<div style="font-family: Monaco; font-size: 11px;">fiveEuros.setYear(<span style="color: #3e38f5;">"1880"</span>);</div>
</fieldset>
<p><br /> Which seems broken and has lots of typing and repetition. This is an example of building a pretty big &nbsp;value object in my opinion, most of tend to be very small.<br /> <br /> Before we talk about the benefits of creating objects this way, let's have a look at the structure of this pattern:</p>
<fieldset style="border-color: #adff2f; border-style: dashed; font-size: 14px;"><br />
<div style="font-family: Monaco; font-size: 11px;"><span style="color: #941965;">public final&nbsp;</span><span style="color: #941965;">class</span>&nbsp;Money {</div>
&nbsp; &nbsp;<br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">Long value;</span><br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">String countryOfOrigin;</span>&nbsp; &nbsp; &nbsp;<br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">Currency currency;</span><br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">String type;</span>&nbsp; <br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">String reverse;</span><br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">String obverse;</span>&nbsp; &nbsp;&nbsp; <br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">List&lt;String&gt; colors;</span><br /> <span style="color: #941965; font-family: Monaco; font-size: 11px;">&nbsp; &nbsp;&nbsp; private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">Date year;</span>&nbsp; &nbsp;&nbsp; <br /> &nbsp;<br /> &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965; font-family: Monaco; font-size: 11px;">private&nbsp;</span><span style="font-family: Monaco; font-size: 11px;">Money() { &nbsp; }</span><br /> <br /> &nbsp; &nbsp; &nbsp;<span style="color: #4d9075; font-family: Monaco; font-size: 11px;">// -- getters, hashCode, equals -- //</span><br /> <br /> &nbsp; &nbsp; &nbsp;<span style="color: #4d9075; font-family: Monaco; font-size: 11px;">// Static inner Builder class</span><br />
<div style="font-family: Monaco; font-size: 11px;">
<div style="color: #941965;">&nbsp; &nbsp;publicstaticclass<span style="color: black;"> Builder {</span></div>
&nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #941965;">private</span>&nbsp;Money&nbsp;<span style="color: #102bc3;">_temp</span> = <span style="color: #941965;">new</span>&nbsp;Money();<br />
<div style="min-height: 15px;">&nbsp;</div>
<span style="color: #941965;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span><span style="color: #941965;">public</span> Builder countryOfOrigin(String countryOfOrigin) {<br /> <span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">contryOfOrigin</span> =&nbsp;countryOfOrigin;<br />
<div style="color: #941965;"><span style="color: black;">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span>returnthis<span style="color: black;">;</span></div>
}<br />
<div style="min-height: 15px;">&nbsp;</div>
<span style="color: #941965;">public</span> Builder currency(Currency c) {<br /> <span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">currency</span> = c;<br />
<div style="color: #941965;">returnthis<span style="color: black;">;</span></div>
}<br />
<div style="min-height: 15px;">&nbsp;</div>
<span style="color: #941965;">public</span> Builder type(String t) {<br /> <span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">type</span> = t;<br />
<div style="color: #941965;">returnthis<span style="color: black;">;</span></div>
}<br />
<div style="min-height: 15px;">&nbsp;</div>
<span style="color: #941965;">public</span> Builder reverse(String r) {<br /> <span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">reverse</span>&nbsp;= r;<br />
<div style="color: #941965;">returnthis<span style="color: black;">;</span></div>
}<br /> <br /> <br /> <span style="color: #941965;">&nbsp; &nbsp; &nbsp; &nbsp;public</span>&nbsp;Builder obverse(String o) {<br /> <span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">obverse</span>&nbsp;= o;<br />
<div style="color: #941965;">return<span style="color: black;">&nbsp;</span>this<span style="color: black;">;</span></div>
}<br /> <br /> <br /> <span style="color: #941965;">public</span>&nbsp;Builder&nbsp;addColor(String c) {<br /> <span style="color: purple;">if</span>(<span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">colors</span>&nbsp;== <span style="color: #941965;">null</span>) {<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">colors =&nbsp;</span><span style="color: #941965;">new</span><span style="color: #102bc3;">&nbsp;</span>ArrayList&lt;String&gt;();&nbsp;<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;}<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">colors.</span>add(c);<br />
<div style="color: #941965;">return<span style="color: black;">&nbsp;</span>this<span style="color: black;">;</span></div>
}<br />
<div>&nbsp;</div>
<div style="min-height: 15px;">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;p<span style="color: #941965;">ublic</span>&nbsp;Builder year(String y) {</div>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: purple;">if</span>(y ==&nbsp;<span style="color: purple;">null</span>&nbsp;|| y.isEmpty()) {<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">year</span>&nbsp;= <span style="color: purple;">new&nbsp;</span>Date();<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: purple;">else</span> {<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: #102bc3;">_temp</span>.<span style="color: #102bc3;">year</span>&nbsp;= DateFormat.parse(y);<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }<br />
<div style="color: #941965;">return<span style="color: black;">&nbsp;</span>this<span style="color: black;">;</span></div>
}<br />
<div style="min-height: 15px;">&nbsp;</div>
<span style="color: #941965;">public</span>&nbsp;Money build() {<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;<span style="font-family: Times; font-size: 14px;">&nbsp;</span><span style="color: #4d9075;">// Validate object</span><br /> <span style="color: #4d9075;">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span style="color: purple;">if</span>(Strings.isNullOrEmpty(_temp.<span style="color: blue;">name</span>)&nbsp;|| _temp.<span style="color: blue;">currency</span> == <span style="color: purple;">null</span>) {<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp;<span style="color: purple;">throw new </span>IllegalArgumentException(<span style="color: #3e38f5;">"Coin currency and value required"</span>);<br /> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;}<br />
<div style="color: #941965;">return<span style="color: #102bc3;">_temp</span><span style="color: black;">;</span></div>
}<br /> &nbsp; &nbsp; } }</div>
</fieldset>
<p><br /> This is also a matter of taste, but I prefer the <em>static inner class</em>&nbsp;approach. I like the canonical nature of referring to the builder as <em>Money.Builder. </em>Also making it <em>static</em>&nbsp;is required since the builder instance needs to live independently of the enclosing class.<br /> <br /> I like this pattern because it has the following benefits:</p>
<ol>
<li><strong>Greater object encapsulation:</strong>&nbsp;I can easily enforce object construction using builders&nbsp;by making the <em>Money </em>constructor&nbsp;private (this is just stylistic). This completely hides all of the intricacies of creating this object: list creation, date parsing, etc. From the user's perspective, what we end up with is an object that is simple to instantiate. My illustration is a very simple one, but imagine more complex object graphs.</li>
<li><strong>Code readability: </strong>Using this pattern to create objects, makes unit tests and code very easy to read and follow.&nbsp;</li>
<li><strong>Less typing in the long run:</strong>&nbsp;Even though you have to add an extra builder method for every added attributes, the amount of typing you save in the long run makes it worth while.&nbsp;</li>
</ol>
<p><br /> <strong>Conclusion</strong><br /> <strong><br /></strong> Using the fluent creation pattern is more work up front, but the benefits of having it pays off at the end. It makes instantiating objects very elegant and clean. You don't have to use it with <em>Value Objects</em>, most of the benefit of using&nbsp;<em>Fluent Object Creation</em>&nbsp;is when you need to build pretty complex object graphs, but I wanted to show that it can also suit<em>&nbsp;</em>small value objects.</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>refer:http://www.reflectivethought.net/2013/01/fluent-object-creation.html</p>
