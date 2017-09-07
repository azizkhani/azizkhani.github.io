---
layout: post
title: "angular.module"
comments: true
---
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;">Using&nbsp;<code style="margin: 0px; padding: 1px 5px; border: 0px; font-size: 13px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; white-space: pre-wrap;">angular.module()</code>&nbsp;with two parameters (e.g.&nbsp;<code style="margin: 0px; padding: 1px 5px; border: 0px; font-size: 13px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; white-space: pre-wrap;">angular.module('aziz-module', [])</code>) would result in&nbsp;<strong style="margin: 0px; padding: 0px; border: 0px;">setting</strong>&nbsp;a new module with its corresponding dependencies. In contrast, when using&nbsp;<code style="margin: 0px; padding: 1px 5px; border: 0px; font-size: 13px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; white-space: pre-wrap;">angular.module('aziz')</code>&nbsp;the corresponding module is looked up internally and returned to the caller (<strong style="margin: 0px; padding: 0px; border: 0px;">getting</strong>).</p>
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;">The means when you first define you application you might just create the following files and structure.</p>
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;"><strong style="margin: 0px; padding: 0px; border: 0px;">app.js</strong></p>
<pre class="default prettyprint prettyprinted" style="margin: 0px 0px 1em; padding: 5px; border: 0px; font-size: 13px; width: auto; max-height: 600px; overflow: auto; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; color: #393318; word-wrap: normal;"><code style="margin: 0px; padding: 0px; border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; white-space: inherit;"><span class="pln" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">angular</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">.</span><span class="kwd" style="margin: 0px; padding: 0px; border: 0px; color: #101094;">module</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">(</span><span class="str" style="margin: 0px; padding: 0px; border: 0px; color: #7d2727;">'myApp'</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">,</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">[]);</span></code></pre>
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;"><strong style="margin: 0px; padding: 0px; border: 0px;">FirstController.js</strong></p>
<pre class="default prettyprint prettyprinted" style="margin: 0px 0px 1em; padding: 5px; border: 0px; font-size: 13px; width: auto; max-height: 600px; overflow: auto; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; color: #393318; word-wrap: normal;"><code style="margin: 0px; padding: 0px; border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; white-space: inherit;"><span class="pln" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">angular</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">.</span><span class="kwd" style="margin: 0px; padding: 0px; border: 0px; color: #101094;">module</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">(</span><span class="str" style="margin: 0px; padding: 0px; border: 0px; color: #7d2727;">'myApp'</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">).</span><span class="pln" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">controller</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">(</span><span class="str" style="margin: 0px; padding: 0px; border: 0px; color: #7d2727;">'FirstController'</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">,</span><span class="kwd" style="margin: 0px; padding: 0px; border: 0px; color: #101094;">function</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">()</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">{});</span></code></pre>
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;"><strong style="margin: 0px; padding: 0px; border: 0px;">SecondController.js</strong></p>
<pre class="default prettyprint prettyprinted" style="margin: 0px 0px 1em; padding: 5px; border: 0px; font-size: 13px; width: auto; max-height: 600px; overflow: auto; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; background-color: #eff0f1; color: #393318; word-wrap: normal;"><code style="margin: 0px; padding: 0px; border: 0px; font-family: Consolas, Menlo, Monaco, 'Lucida Console', 'Liberation Mono', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', 'Courier New', monospace, sans-serif; white-space: inherit;"><span class="pln" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">angular</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">.</span><span class="kwd" style="margin: 0px; padding: 0px; border: 0px; color: #101094;">module</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">(</span><span class="str" style="margin: 0px; padding: 0px; border: 0px; color: #7d2727;">'myApp'</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">).</span><span class="pln" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">controller</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">(</span><span class="str" style="margin: 0px; padding: 0px; border: 0px; color: #7d2727;">'SecondController'</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">,</span><span class="kwd" style="margin: 0px; padding: 0px; border: 0px; color: #101094;">function</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">()</span><span class="pun" style="margin: 0px; padding: 0px; border: 0px; color: #303336;">{});</span></code></pre>
<p style="margin: 0px 0px 1em; padding: 0px; border: 0px; font-size: 15px; clear: both; color: #242729; font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;">If you now include these files in your html document in this particularly order (at least&nbsp;<strong style="margin: 0px; padding: 0px; border: 0px;">app.js</strong>&nbsp;has to come first), your application works just fine with two separate controllers in two separate files.</p>