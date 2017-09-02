---
layout: post
title: "Checked or Unchecked Exceptions?"
comments: true
---
<p><span style="font-size: small;">Some Java books(*) covering exceptions advice you to use checked exceptions for all errors the application can recover from, and unchecked exceptions for the errors the application cannot recover from. In reality most applications will have to recover from pretty much all exceptions including NullPointerException, IllegalArgumentExceptions and many other unchecked exceptions.</span></p>
<p><span style="font-size: small;"><br /></span></p>
<p><br /><span style="font-size: small;">The differences between checked and unchecked exceptions are: </span></p>
<ol>
<li><span style="font-size: small;">Checked exceptions must be explicitly caught or propagated as described in . Unchecked exceptions do not have this requirement. They don't have to be caught or declared thrown. </span>Basic try-catch-finally Exception Handling<br /><br /></li>
<li><span style="font-size: small;">Checked exceptions in Java extend the java.lang.Exception class. Unchecked exceptions extend the java.lang.RuntimeException.</span></li>
</ol>
<p>&nbsp;<strong>Checked</strong></p>
<pre class="brush: java;">public class BadUrlException extends Exception {
        public BadUrlException(String s) {
            super(s);
        }
    }<br /><br /><br /> public void storeDataFromUrl(String url){
        try {
            String data = readDataFromUrl(url);
        } catch (BadUrlException e) {
            e.printStackTrace();
        }
    }

    public String readDataFromUrl(String url)
    throws BadUrlException{
        if(isUrlBad(url)){
            throw new BadUrlException("Bad URL: " + url);
        }

        String data = null;
        //read lots of data over HTTP and return
        //it as a String instance.

        return data;
    }
<br /><br /><strong>Unchecked:</strong><br /> public class BadUrlException extends RuntimeException {
        public BadUrlException(String s) {
            super(s);
        }
    }<br /><br />    public void storeDataFromUrl(String url){
        String data = readDataFromUrl(url);
    }

    public String readDataFromUrl(String url) {
        if(isUrlBad(url)){
            throw new BadUrlException("Bad URL: " + url);
        }

        String data = null;
        //read lots of data over HTTP and
        //return it as a String instance.

        return data;
    }</pre>
