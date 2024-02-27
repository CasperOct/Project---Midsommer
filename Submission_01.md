---


---

<h1 id="security-vulnerability-exposed-conducted-a-brute-force-attack-on-a-website-as-a-result-of-its-weak-authentication-in-login-page">Security vulnerability Exposed: Conducted a Brute Force Attack on a Website as a result of its Weak Authentication in Login Page</h1>
<h3 id="severity-critical">Severity: Critical</h3>
<h2 id="issue-description">Issue Description</h2>
<p>A brute force attack on a website is a method employed by malicious actors to gain unauthorized access to user accounts or sensitive information by systematically attempting all possible combinations of usernames and passwords.</p>
<p>This attack targeted the website’s login page, attempting to gain unauthorized access by systematically trying various username and password combinations. This type of attack relies on the attacker’s persistence and computational power to break through the website’s security measures.</p>
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
<p>The following steps indicate a proof of concept outlined in three(3) steps to reproduce and execute the issue.</p>
<p><strong>Step 1:</strong></p>
<p>Discover user credentials by conducting a <strong>WPscan</strong> within the Kali Linux environment, it’s a method for identifying vulnerabilities and gathering information on WordPress sites. By this gained the admin user account’s “username” as “admin” as you can view in the below figure.</p>
<p><a href="https://ibb.co/qBCgvpX"><img src="https://i.ibb.co/Wn0zLfq/1.png" alt="1" border="0"></a></p>
<p><strong>Step 2:</strong></p>
<p>Exploring the targeted website slated for the brute force attack, the aim is to obtain login credentials. Consequently, attention is directed towards accessing the website’s login page. We need to browse the log in page of the website that we are targeted to make the Brute Force Attempt.</p>
<p><a href="https://ibb.co/6rtK3B5"><img src="https://i.ibb.co/7jp3w4F/2.jpg" alt="2" border="0"></a></p>
<p><strong>Step 3:</strong></p>
<p>Navigate to Burp Suite and proceed to <strong>Open browser</strong>. Subsequently, the login page of the website should be accessed initially.</p>
<p><a href="https://ibb.co/7yt22fM"><img src="https://i.ibb.co/YjBppCn/3.png" alt="3" border="0"></a></p>
<p><strong>Step 4:</strong></p>
<p>Following the step of opening the browser and accessing the targeted website’s login page, input the username obtained for the admin account by <strong>WPscan</strong> and Subsequently, enter an incorrect password and at the same time need to click the “<strong>Intercept on</strong>” in <strong>Burp Suite</strong> before try to log in with the credentials.</p>
<p><a href="https://ibb.co/mJX5RtC"><img src="https://i.ibb.co/cJChytc/4.png" alt="4" border="0"></a></p>
<p><a href="https://ibb.co/sbT3T8T"><img src="https://i.ibb.co/JmYkYDY/6.jpg" alt="6" border="0"></a></p>
<p><a href="https://ibb.co/Hzm1jMh"><img src="https://i.ibb.co/C7xNfXP/7.jpg" alt="7" border="0"></a></p>
<p><strong>Step 5:</strong></p>
<p>As shown in the above preceding image, the wrong password entered on the website is visible within Burp Suite under the proxy section.</p>
<p><a href="https://ibb.co/Hzm1jMh"><img src="https://i.ibb.co/C7xNfXP/7.jpg" alt="7" border="0"></a></p>
<p><strong>Step 6:</strong></p>
<p>Upon selecting the “<strong>Sent to Intruder</strong>” field, the interface in Intruder is displayed as shown below. Within this interface, the password entered should be chosen, followed by clicking “<strong>Add</strong>” and need to click “<strong>Start Attack</strong>”.</p>
<p><a href="https://ibb.co/68PtpjR"><img src="https://i.ibb.co/xYjgcxS/10.jpg" alt="10" border="0"></a></p>
<p><strong>Step 6:</strong></p>
<p>Upon selecting the “<strong>Sent to Intruder</strong>” field, the interface in Intruder is displayed as shown below. Within this interface, the password entered should be chosen, followed by clicking “<strong>Add</strong>” and need to click “<strong>Start Attack</strong>”.</p>
<p><a href="https://ibb.co/hLjzFLs"><img src="https://i.ibb.co/LYW7dYS/9.jpg" alt="9" border="0"></a></p>
<p>We can use GitHub common credentials. Using common passwords for brute force attacks on GitHub accounts is a common tactic employed by hackers because it leverages the likelihood that some users will choose easily guessable or commonly used passwords.</p>
<p>Many users unfortunately still use weak or easily guessable passwords such as “password,” “123456,” or common words. Attackers can compile lists of these common passwords and systematically try them against GitHub accounts. GitHub has a vast user base, including individuals, organizations, and companies. This makes it an attractive target for attackers as compromising even a small percentage of accounts can yield valuable information or access to code repositories.</p>
<p>GitHub passwords were utilized for this project to execute the brute force attack.</p>
<p><strong>Step 6:</strong></p>
<p>The subsequent action involves inserting the passwords obtained from GitHub into the designated field under “<strong>Payload settings</strong>” within the Payloads tab of Burp Suite as shown in the below Picture and click “<strong>Start Attack</strong>.”</p>
<p><a href="https://ibb.co/mv9zgGT"><img src="https://i.ibb.co/SQtvGPy/12.jpg" alt="12" border="0"></a></p>
<p>At this point, Burp Suite will identify the correct password if it matches the one utilized by the admin, provided it is included in the provided list.</p>
<p><a href="https://ibb.co/yN2KWQ0"><img src="https://i.ibb.co/6yQGgWY/13.jpg" alt="13" border="0"></a></p>
<p>The below mentioned picture shows the password for the website we have attacked.</p>
<p><a href="https://ibb.co/Nr5yn5m"><img src="https://i.ibb.co/T16gq6b/14.jpg" alt="14" border="0"></a></p>
<p><strong>Step 6:</strong></p>
<p>By utilizing the discovered username and password, successful access to the website admin panel can be achieved.</p>
<h2 id="business-impact">Business Impact</h2>
<p><strong>Data Breach:</strong> Successful brute force attacks can breach sensitive data like customer information and financial records, leading to legal liabilities, regulatory fines, and reputational damage.</p>
<p><strong>Financial Losses:</strong> Brute force attacks may result in theft of funds, regulatory penalties, remediation costs, and potential loss of business, amplifying financial strain.</p>
<p><strong>Operational Disruption:</strong> Compromised systems can disrupt operations, causing productivity loss, missed deadlines, and revenue decline, particularly impacting organizations heavily reliant on IT infrastructure.</p>
<p><strong>Reputational Damage:</strong> Publicized breaches damage trust, leading to decreased sales, client loss, and difficulty attracting new customers or partners.</p>
<p><strong>Legal and Regulatory Consequences</strong>: Breached data may prompt legal action, resulting in fines, legal fees, and ongoing compliance requirements to prevent future incidents.</p>
<p><strong>Increased Security Costs:</strong> Post-attack, organizations often invest in stronger security measures like authentication mechanisms, audits, staff training, and personnel hiring to mitigate future risks, increasing operational expenses.</p>
<h2 id="recommendation">Recommendation</h2>
<p><strong>Strong Passwords</strong>: Encourage users to create complex passwords with a mix of letters, numbers, and symbols.</p>
<p><strong>Account Lockout Policies</strong>: Set up systems to lock user accounts after a certain number of failed login attempts.</p>
<p><strong>Multi-Factor Authentication (MFA)</strong>: Require additional verification steps, like a code sent to a mobile device, along with passwords for logging in.</p>
<p><strong>Regular Monitoring</strong>: Monitor login attempts for unusual patterns, such as numerous failed logins in a short period.</p>
<p><strong>Limit Login Attempts</strong>: Restrict the number of login attempts allowed within a specific timeframe to deter brute force attacks.</p>
<p><strong>Software Updates</strong>: Keep systems and software updated with the latest security patches to mitigate potential vulnerabilities exploited in brute force attacks.</p>
<p>Implement a password throttling mechanism. This mechanism should take into account both the IP address and the login name of the user.</p>
<p>Put together a strong password policy and make sure that all user created passwords comply with it. Alternatively, automatically generate strong passwords for users.<br>
Passwords need to be recycled to prevent aging, that is every once in a while, a new password must be chosen.</p>
<h2 id="references">References</h2>
<ul>
<li>
<p><a href="https://capec.mitre.org/data/definitions/49.html">https://capec.mitre.org/data/definitions/49.html</a></p>
</li>
<li>
<p><a href="https://owasp.org/www-community/controls/Blocking_Brute_Force_Attacks">https://owasp.org/www-community/controls/Blocking_Brute_Force_Attacks</a></p>
</li>
<li>
<p><a href="https://www.covertswarm.com/post/brute-force-attack">https://www.covertswarm.com/post/brute-force-attack</a></p>
</li>
<li>
<p><a href="https://sucuri.net/guides/what-is-brute-force-attack/">https://sucuri.net/guides/what-is-brute-force-attack/</a></p>
</li>
</ul>

