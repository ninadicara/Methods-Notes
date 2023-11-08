#codefirstgirls MOOC

## Session 2 - OWASP Top 10

OWASP Top 10 - list of ten most common/concerning cyber security issues. Regularly updated. 
## Session 3 - Testing 

### Auto testing applications

Two different ways to auto-analyse vulnerabilities. 

Static Analysis or Dynamic Analysis. 
- Static won't work for dynamically typed languages like JavaScript. 
- Or for chained functionality

Free Static Tools:
- [Bandit](https://bandit.readthedocs.io/en/latest/) [[Python]]
- [Snyk](https://snyk.io/product/snyk-code/) 
Advantages: quick, can be built into CI pipelines (e.g. Snyk with GitHub)

Free Dynamic Tools:
- OWASP ZAP - free and open source
- [Burp Suite](https://portswigger.net/burp) - not open source but has a free tier
Advantages: evaluates programmes at run time/post execution

**REMEMBER** 
Don't use any of these tools on public websites, or anywhere you don't have explicit permission. It's illegal. 

[OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) is a website with security vulnerabilities specifically made available for training and testing. 

### Testing Environment

Most people (professional or otherwise!) use _Kali Linux_, a specific linux distribution made for pen testing. 
Testing inside a container/virtual machine then means you aren't interfering with your local machine or picking up anything that is unrelated to what you're testing. 

Also don't test things like juice box live because the automated testing apps essentially cause a _Denial of Service (DOS)_ by flooding the app with all the different tests. Use local host. 

Another useful tool is [TryHackMe](https://tryhackme.com/) - has lots of learning activities. 

To use OWASP ZAP traffic should be routed through a proxy. You can then use quick start or 'run automated scan'. 

## Session 4 - API Security

Always balancing the CIA triad - confidentiality, integrity and availability.

Notes on specific [OWASP API Top 10](https://owasp.org/API-Security/editions/2023/en/0x11-t10/) risks and mitigations are in the [[APIs (Application Programming Interface)]] note. 

----
These notes are from the Intro To Web App Security MOOC I did with #codefirstgirls in October 2023. 





