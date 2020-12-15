# Attacks

## Man in the middle attack (MITM)

![](https://www.imperva.com/learn/wp-content/uploads/sites/13/2017/09/man-in-the-middle-mitm-attack.png)

### What is MITM attack
A man in the middle (MITM) attack is a general term for when a perpetrator positions himself in a conversation between a user and an application—either to eavesdrop or to impersonate one of the parties, making it appear as if a normal exchange of information is underway.

### How to prevent man in the middle (MITM) Attacks

Detecting man in the middle attacks may be a challenge but luckily, you can follow a simple 10-step guide to prevent them from ever happening. Below you can find the 10 steps to follow in order to prevent man in the middle attacks.

* Educate your employees regarding the most common cyber attacks, cyber threats and what they should to avoid compromising the security of your organization.
* Make sure that your employees don’t use public networks.
* Employ VPNs (Virtual Private Network) in order to ensure the secure connections from your organization.
* Secure your e-mails by employing SSL/TLS. Moreover, you can also consider PGP/GPG encryption as well.
* Make a habit of regularly auditing your networks and devices. Also monitor the activity there so that you can instantly notice any unusual activities.
* Don’t forget to update your browsers. Make sure that your organization always uses the latest version of secure browsers.
* Get browser plugins like ForceTLS of HTTPS Everywhere to secure the sensitive online transactions.
* Separate your Wi-Fi networks. Make sure that guests don’t use your internal network.
* Install high technology, capable intrusion detection systems.
* Implement two-factor authentication.

## What is cross-site scripting (XSS)?


### Cross-Site Scripting (XSS) attacks
   Cross-site Scripting (XSS) is a client-side code injection attack. The attacker aims to execute malicious scripts in a web browser of the victim by including malicious code in a legitimate web page or web application. The actual attack occurs when the victim visits the web page or web application that executes the malicious code. The web page or web application becomes a vehicle to deliver the malicious script to the user’s browser. Vulnerable vehicles that are commonly used for Cross-site Scripting attacks are forums, message boards, and web pages that allow comments.

### **What are the types of XSS attacks?**

There are three main types of XSS attacks. These are:

- Reflected XSS: where the malicious script comes from the current HTTP request.
- Stored XSS: where the malicious script comes from the website's database.
- DOM-based XSS: where the vulnerability exists in client-side code rather than server-side code.

### **How to prevent XSS attacks?**

- Filter input (Escaping and validating): At the point where user input is received, filter as strictly as possible based on what is expected or valid input.

- Encode data on output: At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.

- Use appropriate response headers: To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.

- Content Security Policy: As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.


 ## Cross-Site Request Forgery


Cross-Site Request Forgery (CSRF) is a type of attack that occurs when a malicious web site, email, blog, instant message, or program causes a user’s web browser to perform an unwanted action on a trusted site when the user is authenticated.

A CSRF attack works because browser requests automatically include any credentials associated with the site, such as the user's session cookie, IP address, etc.

Therefore, if the user is authenticated to the site, the site cannot distinguish between the forged or legitimate request sent by the victim.

In effect, CSRF attacks are used by an attacker to make a target system perform a function via the target's browser, without the user’s knowledge, at least until the unauthorized transaction has been committed.

The impact of a successful CSRF attack is limited to the capabilities exposed by the vulnerable application.

    
### How to prevent CSRF attaks: 

### Implement an Anti-CSRF Token
  An anti-CSRF token is a type of CSRF protection. It is a random string that is only known by the user’s browser and the web application. The anti-CSRF token is usually stored inside a session variable. It is typically on a page inside a hidden form field which is sent together with the request.

  If the value of the session variable and the hidden form field match, the web application accepts the request. If they do not match the request is dropped. Since in this case, the attacker does not know the exact value of the hidden form field that is needed for the request to be accepted, he cannot launch a CSRF attack.

### Use the Same-Site Flag in Cookies
  The Same-Site Flag in Cookies is a relatively new method that is being used to prevent CSRF attacks and improve web application security. In the above scenario, we saw that https://attacker.com/could send a POST request to https://example.com/ together with a session cookie. This session cookie is unique for every user and the web application uses it to distinguish different users from each other, and to determine if you are logged in.  