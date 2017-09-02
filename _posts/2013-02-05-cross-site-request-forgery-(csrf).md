---
layout: post
title: "Cross-Site Request Forgery (CSRF)"
comments: true
---
<p>Nowadays, web application security is one of the most important issues in the information system development process. According to Gartner [1] the 75% of the attacks performed nowadays are aimed to web applications, because operative system security and net level security have increased considerably. As a result, it is considered that the 95% of the web applications are vulnerable to a certain type of attack [2]. In the following chart we can see the list of the most important vulnerabilities published by OWASP (Open Web Application Security Project)</p>
<p>&nbsp;</p>
<p><img style="display: block; margin-left: auto; margin-right: auto;" src="/IMAGES/2013/02/687474703a2f2f7777772e686469762e6f72672f696d672f6769746875622f77696b692f63686170746572312f6f77617370746f7074656e2e706e67.png.jpgx" alt="" /></p>
<p>Cross-site request forgery, also known as one click attack or session riding and abbreviated as CSRF (Sea-Surf) or XSRF, is a type of malicious exploit of websites. Although this type of attack has similarities to cross-site scripting (XSS), cross-site scripting requires the attacker to inject unauthorized code into a website, while cross-site request forgery merely transmits unauthorized commands from a user the website trusts.</p>
<p>The attack works by including a link or script in a page that accesses a site to which the user is known (or is supposed) to have authenticated.</p>
<p><strong>Example:</strong> One user, Bob, might be browsing a chat forum where another user, Mallory, has posted a message. Suppose that Mallory has crafted an HTML image element that references a script on Bob's bank's website (rather than an image file), e.g.,</p>
<p><img src="https://a248.e.akamai.net/camo.github.com/20e9dda3c9c0cdcdb45cfe60a18b26c66b0799fb/687474703a2f2f7777772e686469762e6f72672f696d672f6769746875622f77696b692f63686170746572312f637372662e706e67" alt="CSRF" /></p>
<p>If Bob's bank keeps his authentication information in a cookie, and if the cookie hasn't expired, then Bob's browser's attempt to load the image will submit the withdrawal form with his cookie, thus authorizing a transaction without Bob's approval.</p>
<p>A cross-site request forgery is a confused deputy attack against a Web browser. The deputy in the bank example is Bob's Web browser which is confused into misusing Bob's authority at Mallory's direction.</p>
<p>The following characteristics are common to CSRF:</p>
<ul>
<li>Involve sites that rely on a user's identity</li>
<li>Exploit the site's trust in that identity</li>
<li>Trick the user's browser into sending HTTP requests to a target site</li>
<li>Involve HTTP requests that have side effects</li>
</ul>
<p>At risk are web applications that perform actions based on input from trusted and authenticated users without requiring the user to authorize the specific action. A user that is authenticated by a cookie saved in his web browser could unknowingly send an HTTP request to a site that trusts him and thereby cause an unwanted action.</p>
<p>CSRF attacks using images are often made from Internet forums, where users are allowed to post images but not JavaScript.</p>
<h3><strong>Effects</strong></h3>
<p>This attack relies on a few assumptions:</p>
<ul>
<li>The attacker has knowledge of sites the victim has current authentication on (more common on web forums, where this attack is most common)</li>
<li>The attacker's "target site" has persistent authentication cookies, or the victim has a current session cookie with the target site</li>
<li>The "target site" doesn't have secondary authentication for actions (such as form tokens)</li>
</ul>
<p>While having potential for harm, the effect is mitigated by the attacker's need to "know his audience" such that he attacks a small familiar community of victims, or a more common "target site" has poorly implemented authentication systems (for instance, if a common book reseller offers 'instant' purchases without re-authentication).</p>
<h3><strong>Protection</strong></h3>
<p>Applications must ensure that they are not relying on credentials or tokens that are automatically submitted by browsers. The only solution is to use a custom token that the browser will not &lsquo;remember&rsquo; and then automatically include with a CSRF attack.</p>
<p>The following strategies should be inherent in all web applications:</p>
<ul>
<li>Ensure that there are no XSS vulnerabilities in your application.</li>
<li>
<p>Insert custom random tokens into every form and URL that will not be automatically submitted by the browser. For example,</p>
<p><img src="https://a248.e.akamai.net/camo.github.com/422dd1448f4065d0eac9783fba22766c6f32b5e5/687474703a2f2f7777772e686469762e6f72672f696d672f6769746875622f77696b692f63686170746572312f637372662d70726f74656374696f6e2e706e67" alt="CSRF protection" /></p>
<p>and then verify that the submitted token is correct for the current user. Such tokens can be unique to that particular function or page for that user, or simply unique to the overall session. The more focused the token is to a particular function and/or particular set of data, the stronger the protection will be, but the more complicated it will be to construct and maintain.</p>
</li>
<li>
<p>For sensitive data or value transactions, re-authenticate or use transaction signing to ensure that the request is genuine. Set up external mechanisms such as e-mail or phone contact in order to verify requests or notify the user of the request.</p>
</li>
<li>
<p>Do not use GET requests (URLs) for sensitive data or to perform value transactions. Use only POST methods when processing sensitive data from the user. However, the URL may contain the random token as this creates a unique URL, which makes CSRF almost impossible to perform.</p>
</li>
<li>
<p>POST alone is insufficient a protection. You must also combine it with random tokens, out of band authentication or re-authentication to properly protect against CSRF.</p>
</li>
</ul>
<p>While these suggestions will diminish your exposure dramatically, advanced CSRF attacks can bypass many of these restrictions. The strongest technique is the use of unique tokens, and eliminating all XSS vulnerabilities in your application.</p>
<p>It should be noted that <strong>preventing CSRF requires that all XSS problems are removed first</strong>. An XSS flaw can be used to retrieve the form, then grab the random tokens before submitting the CSRF request. XSS may also be able to spoof the user into entering their credentials, which would allow the CSRF to bypass re-authentication as well.</p>
<p>CSRF has been called the "sleeping giant" of web application security flaws, because it has yet to be exploited widely. It is only a matter of time, web programmers should be making the changes needed to ensure that their sites are not vulnerable.</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p><span style="font-size: large;">and now ...... http://hdiv.org/index.htm</span>&nbsp;&nbsp;&nbsp; :D</p>
