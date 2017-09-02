---
layout: post
title: "google precondition validation"
comments: true
---
<p style="text-align: right;"><span style="font-size: large;">حتما تاحالا پیش اومده که بخواهید مقدار ارسال شده به یک متد را ارزیابی کنید تا به خطاهای متداول</span></p>
<p style="text-align: right;"><span style="font-size: large;"><br /></span></p>
<p style="text-align: right;"><span style="font-size: large;">NullPointer</span></p>
<p style="text-align: right;"><span style="font-size: large;"><br />IndexOutOfBound</span></p>
<p style="text-align: right;"><span style="font-size: large;"><br />و از این قبیل بر نخورید به نظرتون روش های انجام این کار در حالت ساده در یک متد چیه؟<br /></span></p>
<h3>Before:</h3>
<pre class="brush: java;">public Delivery createDelivery(Order order,User deliveryPerson){
   if(order.getAddress()==null){
     throw new NullPointerException("order address");
   }
   if(!workSchedule.isOnDuty(deliveryPerson, order.getArrivalTime())){
     throw new IllegalArgumentException(
         String.format("%s is not on duty for %s", deliveryPerson, order));
   }

   return new RealDelivery(order, deliveryPerson);
 }</pre>
<p style="text-align: right;"><span style="font-size: large; direction: rtl;">ولی راه حل ساده تری هم است تا این رفتارها را در یک سری متدهای استاتیک بگذاریم و اون متد را صدا بزنیم ولی برای اینکار شرکت گوگل یک راه در قالب</span></p>
<p style="text-align: right;"><span style="font-size: large; direction: rtl;"><br /></span></p>
<p style="text-align: right;"><span style="font-size: large; direction: rtl;">precondition</span></p>
<p style="text-align: right;"><span style="font-size: large; direction: rtl;"><br />ارایه کرده البیته در قالب</span></p>
<p style="text-align: right;"><span style="font-size: large; direction: rtl;"><br /></span> <span style="font-size: 32pt; font-family: 'ArialMT'; color: #333333;"><span style="font-size: small;">Google's Core Libraries for Java</span></span></p>
<p style="text-align: right;"><span style="font-size: 32pt; font-family: 'ArialMT'; color: #333333;"><br /><span style="font-size: medium;">حالا راه حل قبلی را با کد زیر مقایسه کنید</span></span><span style="font-size: large; direction: rtl;">&nbsp; </span></p>
<p style="text-align: right;">&nbsp;</p>
<h3>After:</h3>
<pre class="brush: java;">publicDelivery createDelivery(Order order,User deliveryPerson){
   Preconditions.checkNotNull(order.getAddress(),"order address");
   Preconditions.checkArgument(workSchedule.isOnDuty(deliveryPerson, order.getArrivalTime()), "%s is not on duty for %s", deliveryPerson, order);

   return new RealDelivery(order, deliveryPerson);
 }</pre>
<p><a name="method_summary"></a></p>
<table style="width: 100%;" summary="" border="1" cellspacing="0" cellpadding="3">
<tbody>
<tr class="TableHeadingColor" bgcolor="#CCCCFF"><th colspan="2" align="left"><span style="font-size: x-small;"> <strong>Method Summary</strong></span></th></tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkArgument%28boolean%29">checkArgument</a></strong>(boolean&nbsp;expression)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving one or more parameters to the calling method.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkArgument%28boolean,%20java.lang.Object%29">checkArgument</a></strong>(boolean&nbsp;expression, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>&nbsp;errorMessage)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving one or more parameters to the calling method.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkArgument%28boolean,%20java.lang.String,%20java.lang.Object...%29">checkArgument</a></strong>(boolean&nbsp;expression, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/String.html?is-external=true">String</a>&nbsp;errorMessageTemplate, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>...&nbsp;errorMessageArgs)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving one or more parameters to the calling method.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;int</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkElementIndex%28int,%20int%29">checkElementIndex</a></strong>(int&nbsp;index, int&nbsp;size)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that <code>index</code> specifies a valid <em>element</em> in an array, list or string of size <code>size</code>.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;int</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkElementIndex%28int,%20int,%20java.lang.String%29">checkElementIndex</a></strong>(int&nbsp;index, int&nbsp;size, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/String.html?is-external=true">String</a>&nbsp;desc)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that <code>index</code> specifies a valid <em>element</em> in an array, list or string of size <code>size</code>.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span><span> <code>static</code></span></span>
<table summary="" border="0" cellspacing="0" cellpadding="0">
<tbody>
<tr align="right" valign="">
<td nowrap="nowrap"><span> <code>&lt;T&gt; T</code></span></td>
</tr>
</tbody>
</table>
</td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkNotNull%28T%29">checkNotNull</a></strong>(T&nbsp;reference)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that an object reference passed as a parameter to the calling method is not null.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span><span> <code>static</code></span></span>
<table summary="" border="0" cellspacing="0" cellpadding="0">
<tbody>
<tr align="right" valign="">
<td nowrap="nowrap"><span> <code>&lt;T&gt; T</code></span></td>
</tr>
</tbody>
</table>
</td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkNotNull%28T,%20java.lang.Object%29">checkNotNull</a></strong>(T&nbsp;reference, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>&nbsp;errorMessage)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that an object reference passed as a parameter to the calling method is not null.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span><span> <code>static</code></span></span>
<table summary="" border="0" cellspacing="0" cellpadding="0">
<tbody>
<tr align="right" valign="">
<td nowrap="nowrap"><span> <code>&lt;T&gt; T</code></span></td>
</tr>
</tbody>
</table>
</td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkNotNull%28T,%20java.lang.String,%20java.lang.Object...%29">checkNotNull</a></strong>(T&nbsp;reference, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/String.html?is-external=true">String</a>&nbsp;errorMessageTemplate, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>...&nbsp;errorMessageArgs)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that an object reference passed as a parameter to the calling method is not null.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;int</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkPositionIndex%28int,%20int%29">checkPositionIndex</a></strong>(int&nbsp;index, int&nbsp;size)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that <code>index</code> specifies a valid <em>position</em> in an array, list or string of size <code>size</code>.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;int</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkPositionIndex%28int,%20int,%20java.lang.String%29">checkPositionIndex</a></strong>(int&nbsp;index, int&nbsp;size, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/String.html?is-external=true">String</a>&nbsp;desc)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that <code>index</code> specifies a valid <em>position</em> in an array, list or string of size <code>size</code>.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkPositionIndexes%28int,%20int,%20int%29">checkPositionIndexes</a></strong>(int&nbsp;start, int&nbsp;end, int&nbsp;size)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures that <code>start</code> and <code>end</code> specify a valid <em>positions</em> in an array, list or string of size <code>size</code>, and are in order.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkState%28boolean%29">checkState</a></strong>(boolean&nbsp;expression)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving the state of the calling instance, but not involving any parameters to the calling method.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkState%28boolean,%20java.lang.Object%29">checkState</a></strong>(boolean&nbsp;expression, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>&nbsp;errorMessage)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving the state of the calling instance, but not involving any parameters to the calling method.</td>
</tr>
<tr class="TableRowColor" bgcolor="white">
<td align="right" valign="top" width="1%"><span> <code>static&nbsp;void</code></span></td>
<td><code><strong><a href="http://google-collections.googlecode.com/svn/trunk/javadoc/com/google/common/base/Preconditions.html#checkState%28boolean,%20java.lang.String,%20java.lang.Object...%29">checkState</a></strong>(boolean&nbsp;expression, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/String.html?is-external=true">String</a>&nbsp;errorMessageTemplate, <a title="class or interface in java.lang" href="http://java.sun.com/javase/6/docs/api/java/lang/Object.html?is-external=true">Object</a>...&nbsp;errorMessageArgs)</code> <br /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ensures the truth of an expression involving the state of the calling instance, but not involving any parameters to the calling method.</td>
</tr>
</tbody>
</table>
<p>&nbsp;<a name="methods_inherited_from_class_java.lang.Object"></a></p>
