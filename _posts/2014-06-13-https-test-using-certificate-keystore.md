---
layout: post
title: "https test using certificate & keystore"
comments: true
---
<p>&nbsp;</p>
<p><span style="color: #000080;">package org.springframework.integration.samples.rest;</span><br /><br /><span style="color: #000080;">import java.io.BufferedReader;</span><br /><span style="color: #000080;">import java.io.InputStream;</span><br /><span style="color: #000080;">import java.io.InputStreamReader;</span><br /><span style="color: #000080;">import java.net.MalformedURLException;</span><br /><span style="color: #000080;">import java.net.URL;</span><br /><br /><span style="color: #000080;">import javax.net.ssl.TrustManager;</span><br /><span style="color: #000080;">import javax.net.ssl.X509TrustManager;</span><br /><br /><span style="color: #000080;">public class HttpsTest {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; public static void main(String[] args) {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; System.setProperty("javax.net.ssl.keyStore","/azizkhani/keystore.jks");</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; System.setProperty("javax.net.ssl.keyStorePassword", "pass");</span><br /><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; // full log for debugging</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; System.setProperty("javax.net.debug", "all");</span><br /><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; try {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; try {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; javax.net.ssl.HttpsURLConnection.setDefaultHostnameVerifier(</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; new javax.net.ssl.HostnameVerifier(){</span><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;<br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; public boolean verify(String hostname,</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; javax.net.ssl.SSLSession sslSession) {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if (hostname.equals("ansarrootca")) {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; return true;</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; return false;</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; }</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; });</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; URL url = new URL("https://site:3443");</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; InputStream is = url.openStream();</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; BufferedReader in = new BufferedReader(new InputStreamReader(is));</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; String inputLine = null;</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; while ((inputLine = in.readLine()) != null)</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; System.out.println(inputLine);</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; in.close();</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; is.close();</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; } catch (MalformedURLException e) {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; e.printStackTrace();</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; }</span><br /><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; } catch (Exception e) {</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; e.printStackTrace();</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; }</span><br /><span style="color: #000080;">&nbsp;&nbsp;&nbsp; }</span><br /><span style="color: #000080;">}</span></p>
<p>&nbsp;</p>