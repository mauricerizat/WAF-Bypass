
# WAF-Bypass

I'm surprised how few articles there are that talk about this rather simple Web Application Firewall bypass. It doesn't require any plugins or such.

You'll need BurpSuite proxy for this.

* Navigate to the **Proxy** tab and then open the **Options** menu.

* Then, in the **Match and Replace** section **Add** the following attributes:

```
x-originating-IP: 127.0.0.1
x-forwarded-for: 127.0.0.1
x-remote-IP: 127.0.0.1
x-remote-addr: 127.0.0.1
```
Usually the x-originating-IP and x-forwarded-for attributes play the greatest role in tricking the WAF.

Reference: https://owasp.org/www-pdf-archive/OWASP_Stammtisch_Frankfurt_-_Web_Application_Firewall_Bypassing_-_how_to_defeat_the_blue_team_-_2015.10.29.pdf
