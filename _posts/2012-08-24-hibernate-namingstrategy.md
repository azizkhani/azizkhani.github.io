---
layout: post
title: "Hibernate NamingStrategy"
comments: true
---
<p style="text-align: right;"><span style="font-size: medium;">حتما تا حالا در مورد این قضیه فکر کردید که در هایبرنت کاش میشد یه کاری کنیم که نام گذاریهای تولید شده برای</span></p>
<p style="text-align: right;"><span style="font-size: medium;">table,constraint,.. </span></p>
<p style="text-align: right;"><span style="font-size: medium;">به صورت اتوماتیک و طبق استاندارد مشخصی که خودمون تعریف میکنیم باشه برای مثال اول نام جدول </span></p>
<p style="text-align: right;"><span style="font-size: medium;">tbl</span></p>
<p style="text-align: right;"><span style="font-size: medium;">باشه برای این کار قابلیتی وجود داره که میتون این کار رو انجام بده</span></p>
<p style="text-align: right;"><span style="font-size: medium;">Hibernate NamingStrategy</span></p>
<p style="text-align: right;"><span style="font-size: medium;">کد زیر یک نمونه برای اینکار است که با توجه به محدودیتهای پایگاه داده اراکل(تعداد کاراکتر ۳۰ )برای نام گذاری است پیاده شده</span></p>
<pre class="brush: java;">package org.common.utility;

import org.hibernate.cfg.DefaultComponentSafeNamingStrategy;

import java.util.StringTokenizer;

public class OracleNamingStrategy extends DefaultComponentSafeNamingStrategy {
    private static final long serialVersionUID = -3020615242092992933L;

    protected static String addUnderscores(String name) {
        if (name == null)
            return null;
        StringBuffer buf = new StringBuffer(name.replace('.', '_'));
        for (int i = 1; i &lt; buf.length() - 1; i++) {
            if ((isLowerToUpper(buf, i)) || (isMultipleUpperToLower(buf, i))

            ) {
                buf.insert(i++, '_');
            }
        }
        return buf.toString().toLowerCase();
    }

    private static boolean isMultipleUpperToLower(StringBuffer buf, int i) {
        return i &gt; 1 &amp;&amp; Character.isUpperCase(buf.charAt(i - 1))
                &amp;&amp; Character.isUpperCase(buf.charAt(i - 2))
                &amp;&amp; Character.isLowerCase(buf.charAt(i));
    }

    private static boolean isLowerToUpper(StringBuffer buf, int i) {
        return Character.isLowerCase(buf.charAt(i - 1))
                &amp;&amp; Character.isUpperCase(buf.charAt(i));
    }

    @Override
    public String collectionTableName(String ownerEntity,
            String ownerEntityTable, String associatedEntity,
            String associatedEntityTable, String propertyName) {
        return abbreviateName(super.collectionTableName(
                addUnderscores(ownerEntity), addUnderscores(ownerEntityTable),
                addUnderscores(associatedEntity),
                addUnderscores(associatedEntityTable),
                addUnderscores(propertyName)));
    }

    @Override
    public String foreignKeyColumnName(String propertyName,
            String propertyEntityName, String propertyTableName,
            String referencedColumnName) {
        return abbreviateName(super.foreignKeyColumnName(
                addUnderscores(propertyName),
                addUnderscores(propertyEntityName),
                addUnderscores(propertyTableName),
                addUnderscores(referencedColumnName)));
    }

    @Override
    public String logicalCollectionColumnName(String columnName,
            String propertyName, String referencedColumn) {
        return abbreviateName(super.logicalCollectionColumnName(
                addUnderscores(columnName), addUnderscores(propertyName),
                addUnderscores(referencedColumn)));
    }

    @Override
    public String logicalCollectionTableName(String tableName,
            String ownerEntityTable, String associatedEntityTable,
            String propertyName) {
        return abbreviateName(super.logicalCollectionTableName(
                addUnderscores(tableName), addUnderscores(ownerEntityTable),
                addUnderscores(associatedEntityTable),
                addUnderscores(propertyName)));
    }

    @Override
    public String logicalColumnName(String columnName, String propertyName) {
        return abbreviateName(super.logicalColumnName(
                addUnderscores(columnName), addUnderscores(propertyName)));
    }

    @Override
    public String propertyToColumnName(String propertyName) {
        return abbreviateName(super
                .propertyToColumnName(addUnderscores(propertyName)));
    }

    private static final int MAX_LENGTH = 30;

    public static String abbreviateName(String someName) {
        if (someName.length() &lt;= MAX_LENGTH)
            return someName;

        String[] tokens = splitName(someName);
        shortenName(someName, tokens);

        return assembleResults(tokens);
    }

    private static String[] splitName(String someName) {
        StringTokenizer toki = new StringTokenizer(someName, "_");
        String[] tokens = new String[toki.countTokens()];
        int i = 0;
        while (toki.hasMoreTokens()) {
            tokens[i] = toki.nextToken();
            i++;
        }
        return tokens;
    }

    private static void shortenName(String someName, String[] tokens) {
        int currentLength = someName.length();
        while (currentLength &gt; MAX_LENGTH) {
            int tokenIndex = getIndexOfLongest(tokens);
            String oldToken = tokens[tokenIndex];
            tokens[tokenIndex] = abbreviate(oldToken);
            currentLength -= oldToken.length() - tokens[tokenIndex].length();
        }
    }

    private static String assembleResults(String[] tokens) {
        StringBuilder result = new StringBuilder(tokens[0]);
        for (int j = 1; j &lt; tokens.length; j++) {
            result.append("_").append(tokens[j]);
        }
        return result.toString();
    }

    private static String abbreviate(String token) {
        final String VOWELS = "AEIOUaeiou";
        boolean vowelFound = false;
        for (int i = token.length() - 1; i &gt;= 0; i--) {
            if (!vowelFound)
                vowelFound = VOWELS.contains(String.valueOf(token.charAt(i)));
            else if (!VOWELS.contains(String.valueOf(token.charAt(i))))
                return token.substring(0, i + 1);
        }
        return "";
    }

    private static int getIndexOfLongest(String[] tokens) {
        int maxLength = 0;
        int index = -1;
        for (int i = 0; i &lt; tokens.length; i++) {
            String string = tokens[i];
            if (maxLength &lt; string.length()) {
                maxLength = string.length();
                index = i;
            }
        }
        return index;
    }

    @Override
    public String classToTableName(String aClassName) {

        return abbreviateName(super
                .classToTableName(addUnderscores(aClassName)));
    }
}</pre>
<p style="text-align: right;"><span style="font-size: medium;">حالا باید این را به تنظیمات هایبرنت اضافه کنیم</span></p>
<pre class="brush: xml;">&lt;bean id="sessionFactory"
		class="org.springframework.orm.hibernate4.LocalSessionFactoryBean"&gt;
		&lt;property name="dataSource" ref="dataSource" /&gt;
		&lt;property name="mappingLocations"&gt;
			&lt;list&gt;
				&lt;value&gt;/WEB-INF/classes/hibernate/**/*.hbm.xml&lt;/value&gt;
			&lt;/list&gt;
		&lt;/property&gt;
		<strong>&lt;property name="namingStrategy" ref="namingStrategy" /&gt;</strong>
		&lt;property name="hibernateProperties"&gt;
			&lt;props&gt;
				&lt;prop key="hibernate.connection.driver_class"&gt; ${hibernate.connection.driver_class}&lt;/prop&gt;
				&lt;prop key="hibernate.connection.url"&gt; ${hibernate.connection.url}&lt;/prop&gt;
				&lt;prop key="hibernate.connection.username"&gt; ${hibernate.connection.username}&lt;/prop&gt;
				&lt;prop key="hibernate.connection.password"&gt; ${hibernate.connection.password}&lt;/prop&gt;
				&lt;prop key="hibernate.dialect"&gt; ${hibernate.dialect}&lt;/prop&gt;
				&lt;prop key="hibernate.show_sql"&gt; ${hibernate.show_sql}&lt;/prop&gt;
				&lt;prop key="hibernate.hbm2ddl.auto"&gt; ${hibernate.hbm2ddl_auto}&lt;/prop&gt;
			&lt;/props&gt;
		&lt;/property&gt;
	&lt;/bean&gt;
	&lt;bean id="namingStrategy" class="<strong>org.common.utility.OracleNamingSthrategy</strong>"/&gt;</pre>
