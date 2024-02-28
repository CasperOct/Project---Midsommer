---


---

<h1 id="exploiting-wordpress-plugin-translatepress-2.0.8-for-stored-cross-site-scripting-xss-authenticated">Exploiting WordPress Plugin TranslatePress 2.0.8 for Stored Cross-Site Scripting (XSS) (Authenticated)</h1>
<h3 id="severity-critical">Severity: Critical</h3>
<h2 id="issue-description">Issue Description</h2>
<p>This report provides insights into the exploitation of a critical vulnerability found in WordPress Plugin TranslatePress version 2.0.8. The vulnerability involves Stored Cross-Site Scripting (XSS) attacks, which require authentication. Through detailed analysis and testing, the report outlines how attackers can inject and execute malicious scripts within the website’s context. Such exploits pose significant risks, including compromising user data and manipulating site content. The report emphasizes the urgency of patching and implementing mitigation strategies to protect WordPress websites from potential breaches.</p>
<h2 id="risk-rating">Risk Rating</h2>
<ul>
<li>
<p>Risk: Critical</p>
</li>
<li>
<p>Difficulty to Exploit: Medium</p>
</li>
<li>
<p>Authentication : No</p>
</li>
</ul>
<h2 id="affected-urls">Affected URLs</h2>
<ul>
<li><a href="http://43.205.237.12:31337/">http://43.205.237.12:31337/</a></li>
</ul>
<h2 id="steps-to-reproducepoc">Steps to Reproduce/PoC</h2>
<p>The following steps indicate a proof of concept outlined in steps to reproduce and execute the issue.</p>
<h2 id="proof-of-concept">Proof Of Concept</h2>
<p><strong>Step 1:</strong></p>
<p>To exploit the vulnerability in the “Midsommer” site, the initial step involves executing a brute force attack to obtain the admin credentials. Subsequently, the <strong>WordPress Plugin TranslatePress 2.0.8</strong>, known for its vulnerability to Stored Cross-Site Scripting (XSS) (Authenticated), will be installed.</p>
<p><a href="https://ibb.co/D82gWXS"><img src="https://i.ibb.co/LJ7hRw2/1.jpg" alt="1" border="0"></a></p>
<p><strong>Step 2:</strong></p>
<p>Upon successfully acquiring user credentials through a brute force attack, access to the website will be granted. Subsequently, navigation to the website’s plugins section is required.</p>
<p><a href="https://ibb.co/ySWmT7q"><img src="https://i.ibb.co/TLmDXdt/3.jpg" alt="3" border="0"></a></p>
<p><strong>Step 3:</strong></p>
<p>Accessing the website’s interface, navigate to the “Add New” option and select the previously installed “WordPress Plugin TranslatePress 2.0.8 - Stored Cross-Site Scripting (XSS) (Authenticated)” obtained from the Exploit Database.</p>
<p><a href="https://ibb.co/LSk1K7T"><img src="https://i.ibb.co/tBmDRr0/3.jpg" alt="3" border="0"></a></p>
<p><strong>Step 4:</strong></p>
<p>To activate the plugin, proceed by selecting the “Activate Plugin” option</p>
<p><a href="https://ibb.co/TbrNXZh"><img src="https://i.ibb.co/YybV96j/7.jpg" alt="7" border="0"></a></p>
<p><a href="https://ibb.co/THR7fDh"><img src="https://i.ibb.co/9q21DmY/8.jpg" alt="8" border="0"></a></p>
<p><strong>Step 5:</strong></p>
<p>The image below displays the added plugin, visible for reference.</p>
<p><a href="https://ibb.co/vdXS130"><img src="https://i.ibb.co/Yd0x2cH/9.jpg" alt="9" border="0"></a></p>
<p><strong>Step 6:</strong></p>
<p>Navigate to the “Settings” option located under TranslatePress</p>
<p><a href="https://ibb.co/r676CVB"><img src="https://i.ibb.co/C717kfj/11.jpg" alt="11" border="0"></a></p>
<p><strong>Step 7:</strong><br>
Proceed by selecting “Translate Site” to access a new window, depicted in the image below. Within this window, modify the “From Original String” to “Search” and paste the command into “To English” before saving changes.</p>
<p><a href="https://ibb.co/6P8fxjb"><img src="https://i.ibb.co/0MKdSHZ/16.jpg" alt="16" border="0"></a></p>
<p>Upon saving the translation, triggering an alert will occur whenever a visitor accesses the page</p>
<p><a href="https://ibb.co/BKRyYh8"><img src="https://i.ibb.co/CsFbSjx/17.jpg" alt="17" border="0"></a></p>
<p>As illustrated previously, after saving the translation, an alert labeled “<strong>Sankavi</strong>” will be displayed on the website. This alert persists even upon visiting the main webpage.</p>
<h2 id="business-impact">Business Impact</h2>
<ul>
<li><strong>Data Breach</strong>: Unauthorized access to sensitive data in the WordPress<br>
site’s database.</li>
<li><strong>Loss of Customer Trust:</strong> Damage to customer confidence and reputation due to compromised data.</li>
<li><strong>Financial Loss:</strong> Potential lawsuits, regulatory fines, and remediation costs.</li>
<li><strong>Disruption of Operations:</strong> Downtime for website fixes leading to lost sales and productivity.</li>
<li><strong>Legal and Compliance Issues:</strong> Violations of data protection regulations like GDPR and CCPA.</li>
<li><strong>Reputational Damage:</strong> Tarnished image and long-term trust issues among customers.</li>
<li><strong>Remediation Efforts:</strong> Resources required to fix the vulnerability and restore security.</li>
</ul>
<h2 id="recommendations">Recommendations</h2>
<ul>
<li><strong>Immediate Patching:</strong> Apply the latest security patches provided by TranslatePress to fix the vulnerability.</li>
<li><strong>Regular Updates:</strong> Stay vigilant for plugin updates and promptly install them to mitigate security risks.</li>
<li><strong>Security Audits:</strong> Conduct regular security audits of WordPress plugins to identify and address vulnerabilities proactively.</li>
<li><strong>User Permissions:</strong> Review and restrict user permissions to minimize the impact of potential XSS attacks.</li>
<li><strong>Web Application Firewall (WAF):</strong> Implement a WAF to monitor and filter malicious traffic, including XSS attacks.</li>
<li><strong>Data Encryption:</strong> Encrypt sensitive data stored in the WordPress database to protect it from unauthorized access.</li>
<li><strong>Security Training:</strong> Educate website administrators and users about best practices for preventing XSS attacks and maintaining site<br>
security.</li>
</ul>
<h2 id="references">References</h2>
<ul>
<li>
<p><a href="https://www.synopsys.com/glossary/what-is-cross-site-scripting.html#:~:text=Cross%2Dsite%20scripting%20(XSS)%20is%20an%20attack%20in%20which,the%20user%20to%20click%20it">https://www.synopsys.com/glossary/what-is-cross-site-scripting.html#:~:text=Cross-site scripting (XSS) is an attack in which,the user to click it</a>.</p>
</li>
<li>
<p><a href="https://owasp.org/www-community/attacks/xss/">https://owasp.org/www-community/attacks/xss/</a></p>
</li>
<li>
<p><a href="https://portswigger.net/web-security/cross-site-scripting">https://portswigger.net/web-security/cross-site-scripting</a></p>
</li>
<li>
<p><a href="https://www.imperva.com/learn/application-security/cross-site-scripting-xss-attacks/">https://www.imperva.com/learn/application-security/cross-site-scripting-xss-attacks/</a></p>
</li>
</ul>

