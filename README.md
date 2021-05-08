

# WAF-Bypass

I'm surprised how few articles there are that talk about this rather simple Web Application Firewall bypass. It doesn't require any plugins or such, but this will only work if the WAF is configured exclusively to check the IP addresses of machines connecting to it. Obviously, that may not always be the case.

You'll need BurpSuite proxy for this.

* Navigate to the **Proxy** tab and then open the **Options** menu.
* Then, in the **Match and Replace** section, click **Add** to create a new rule.
* A dialog box will open, so add one of the following attributes in the **replace** field.
```
x-originating-IP: 127.0.0.1
x-forwarded-for: 127.0.0.1
x-remote-IP: 127.0.0.1
x-remote-addr: 127.0.0.1
```
Usually the x-originating-IP and x-forwarded-for attributes play the greatest role in tricking the WAF.

Reference: https://owasp.org/www-pdf-archive/OWASP_Stammtisch_Frankfurt_-_Web_Application_Firewall_Bypassing_-_how_to_defeat_the_blue_team_-_2015.10.29.pdf
