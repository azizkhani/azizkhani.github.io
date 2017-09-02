---
layout: post
title: "setResultTransformer in hibernate "
comments: true
---
<p style="text-align: right; direction: rtl;"><span style="font-size: medium;">یکی از مواردی که حتما در کار کردن با hibernate براتون پیش اومده اینه که یکquery بنویسیدکه نتیجه اون چیزی به غیر از یکی از</span></p>
<p style="text-align: right; direction: rtl;"><span style="font-size: medium;"> domain model شما باشه برای مثال استفاده از دستورات count,sum,و&nbsp; در این حالت باید یک مدل جدید برای نتایج ایجاد کنید برای</span></p>
<p style="text-align: right; direction: rtl;"><span style="font-size: medium;"> مثال اگر شما بخواهید این نتایج را برگدونید باید روش زیر را انجام بدید </span></p>
<pre>&nbsp;</pre>
<pre>Iterator results = sess.createQuery(
        "select cat.color, min(cat.birthdate), count(cat) from Cat cat " +
        "group by cat.color")
        .list()
        .iterator();

while ( results.hasNext() ) {
    Object[] row = (Object[]) results.next();
    Color type = (Color) row[0];
    Date oldest = (Date) row[1];
    Integer count = (Integer) row[2];
    .....
}</pre>
<p style="text-align: right; direction: rtl;"><span style="font-size: medium;">&nbsp;ولی این راه حل مشکلی که داره اینه که اولا وابسته به index نتایج هستید و کلا کار قشنگ و درستی نیست ولی حالا کد زیر را نگاه کنید</span></p>
<pre class="brush: java;">&nbsp;</pre>
<pre class="brush: java;">Query query=sess.createQuery("select cat.color, min(cat.birthdate), count(cat) from Cat cat
group by cat.color").setResultTransformer(Transformers.aliasToBean(YourObject.class));
List&lt;YourObject&gt; lst=query.list();</pre>
<pre class="brush: java;">&nbsp;</pre>
