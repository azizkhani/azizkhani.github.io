---
layout: post
title: "@Platform and @Qualifier"
comments: true
---
<pre><br /><span style="font-size: small;"><span class="k">@<span class="kt">Autowired</span> <br /><span class="k">private</span> <span class="kt">MarketPlace</span> marketPlaces; <br /><br /></span></span><br /><span style="font-size: small;"><span class="k">@<span class="kt">Autowired<br /></span></span></span><span style="font-size: small;"><span class="k"><span class="kt"><strong>@Qualifier( <span class="s2">"ios"</span>) </strong><span class="c1"><strong>// the use is unique to Spring. It's darned convenient, too!</strong><br /></span></span>&nbsp;<span class="k">private</span> <span class="kt">MarketPlace</span> marketPlaces; <br /><br /><br /><br />and now jsr 330<br /><br /><br /><br /><br /></span></span></pre>
<pre class="brush: java;">package spring;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.stereotype.Component;

import javax.annotation.PostConstruct;
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

import static spring.Spring.Platform;

@Configuration
@ComponentScan
public class Spring {

    public static void main(String[] args) {
        new AnnotationConfigApplicationContext(Spring.class);
    }

    @Autowired
<strong> @Platform(Platform.OperatingSystems.ANDROID)</strong>
    private MarketPlace android;

    @Autowired
<strong> @Platform(Platform.OperatingSystems.IOS)</strong>
    private MarketPlace ios;

    @PostConstruct
    public void qualifyTheTweets() {
        System.out.println("ios:" + this.ios);
        System.out.println("android:" + this.android);
    }

    // the type has to be public!
    @Target({ElementType.FIELD,
            ElementType.METHOD,
            ElementType.TYPE,
            ElementType.PARAMETER})
    @Retention(RetentionPolicy.RUNTIME)
    @Qualifier
    public static @interface <strong>Platform</strong> {

        OperatingSystems value();

        public static enum OperatingSystems {
            IOS,
            ANDROID
        }
    }
}

interface MarketPlace {
}

@Component
<strong>@Platform(Platform.OperatingSystems.IOS)</strong>
class AppleMarketPlace implements MarketPlace {

    @Override
    public String toString() {
        return "apple";
    }
}

@Component
<strong>@Platform(Platform.OperatingSystems.ANDROID)</strong>
class GoogleMarketPlace implements MarketPlace {

    @Override
    public String toString() {
        return "android";
    }
}</pre>
