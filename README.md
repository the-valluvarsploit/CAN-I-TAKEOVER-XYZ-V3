![image](https://user-images.githubusercontent.com/18099289/45263787-a4bbc880-b430-11e8-9cff-eb6e4c796050.png)

## Disclaimer :warning:

**The authors of this document take no responsibility for correctness. This project is merely here to help guide security researchers towards determining whether something is vulnerable or not, but does not guarantee accuracy. This project heavily relies on contributions from the public; therefore, proving that something is vulnerable is the security researcher and bug bounty program's sole discretion. On top of that, it is worth noting that some bug bounty programs may accept dangling DNS record reports without requiring proof of compromise.**

## What is a subdomain takeover?

> Subdomain takeover vulnerabilities occur when a subdomain (subdomain.example.com) is pointing to a service (e.g. GitHub pages, Heroku, etc.) that has been removed or deleted. This allows an attacker to set up a page on the service that was being used and point their page to that subdomain. For example, if subdomain.example.com was pointing to a GitHub page and the user decided to delete their GitHub page, an attacker can now create a GitHub page, add a CNAME file containing subdomain.example.com, and claim subdomain.example.com.

You can read up more about subdomain takeovers here:

- <https://labs.detectify.com/2014/10/21/hostile-subdomain-takeover-using-herokugithubdesk-more/>
- <https://www.hackerone.com/blog/Guide-Subdomain-Takeovers>
- <https://0xpatrik.com/subdomain-takeover-ns/>

## Safely demonstrating a subdomain takeover

Based on personal experience, claiming the subdomain discreetly and serving a harmless file on a hidden page is usually enough to demonstrate the security vulnerability. Do not serve content on the index page. A good proof of concept could consist of an HTML comment served via a random path:

```
$ cat aelfjj1or81uegj9ea8z31zro.html
<!-- PoC by username -->
```

Please be advised that this depends on what bug bounty program you are targeting. When in doubt, please refer to the bug bounty program's security policy and/or request clarifications from the team behind the program.

## How to use this project

I recommend searching for the name of the service you are targeting in the issues tab. That way you can see the on-going discussion and more detailed steps on how to claim the subdomain you are after.

## How to contribute

You can submit new services here: https://github.com/the-valluvarsploit/CAN-I-TAKEOVER-XYZ-V3/issues/new.

# All entries

Engine                                        | Status         | Fingerprint                                                             | Discussion                                                    | Documentation
--------------------------------------------- | -------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------
Acquia | Not vulnerable | `Web Site Not Found` |
Agile CRM | Vulnerable | `Sorry, this page is no longer available.` |
Airee.ru                             | Vulnerable     | |  |
Anima | Vulnerable | `If this is your website and you've just created it, try refreshing in a minute` |  | [Anima Documentation](https://docs.animaapp.com/v1/launchpad/08-custom-domain.html)
Akamai                                        | Not vulnerable | |  |
AWS/S3                             | Vulnerable     | `The specified bucket does not exist`                                   | 
AWS/Load Balancer (ELB)                             | Not Vulnerable     | status NXDOMAIN and CNAME pointing to XYZ.elb.amazonaws.com                                 | 
AWS/Elastic Beanstalk                               | Vulnerable         | `404 Not Found`     |                 
Bitbucket                       | Vulnerable     | `Repository not found`                                                  |
Campaign Monitor         | Vulnerable     |               `Trying to access your account?`                                                          |                                                              | [Support Page](https://help.campaignmonitor.com/custom-domain-names)
Cargo Collective         | Vulnerable     | `404 Not Found` |                                                                                                                       | [Cargo Support Page](https://support.2.cargocollective.com/Using-a-Third-Party-Domain)
Cloudfront                     | Not vulnerable      | ViewerCertificateException            |  | [Domain Security on Amazon CloudFront](https://aws.amazon.com/blogs/networking-and-content-delivery/continually-enhancing-domain-security-on-amazon-cloudfront/)
Desk                                 | Not vulnerable     | `Please try again or try Desk.com free for 14 days.`                    | 
Digital Ocean | Vulnerable | Domain uses DO name servers with no records in DO. |   |   |
Discourse | Vulnerable | | | [Hackerone](https://hackerone.com/reports/264494)
Fastly                             | Edge Case     | `Fastly error: unknown domain:`                                         | 
Feedpress                       | Not vulnerable     | `The feed has not been found.`                                          | 
Firebase | Not vulnerable | |  |
Fly.io                             | Vulnerable     | `404 Not Found`                                         | 
Freshdesk                       | Not vulnerable |`We couldn't find servicedesk.victim.tld Maybe this is still fresh! You can claim it now at http://www.freshservice.com/signup`| | [Freshdesk Support Page](https://support.freshdesk.com/support/solutions/articles/37590-using-a-vanity-support-url-and-pointing-the-cname)
Frontify | Edge case | `404 - Page Not Found` `Oops… looks like you got lost` |  | 
Gemfury | Vulnerable | `404: This page could not be found.` |  | [Article](https://khaledibnalwalid.wordpress.com/2020/06/25/gemfury-subdomain-takeover/)
Ghost                               | Vulnerable     | `The thing you were looking for is no longer here, or never was`        | 
Github                             | Edge case     | `There isn't a GitHub Pages site here.`                                 | 
Gitlab                             | Not vulnerable |                                                                         | [HackerOne #312118](https://hackerone.com/reports/312118)
Google Cloud Storage | Not vulnerable |   <?xml version='1.0' encoding='UTF-8'?><Error><Code>NoSuchBucket</Code><Message>The specified bucket does not exist.</Message></Error>   
Google Sites                           | Not vulnerable     | `The requested URL was not found on this server. That’s all we know.`                                                    |  | [Google Support](https://support.google.com/webmasters/answer/9008080?visit_id=637981741431097680-3818919062&rd=2)|
HatenaBlog | vulnerable | `404 Blog is not found`                                                                         |
Help Juice                     | Vulnerable     | `We could not find what you're looking for.`                            |                                                               | [Help Juice Support Page](https://help.helpjuice.com/en_US/using-your-custom-domain/how-to-set-up-a-custom-domain)
Help Scout                     | Vulnerable     | `No settings were found for this company:`                              |                                                               | [HelpScout Docs](https://docs.helpscout.net/article/42-setup-custom-domain)
Heroku                             | Edge case     | `No such app`                                                           | 
HubSpot                            | Not vulnerable | `This page isn’t available`
Instapage | Not vulnerable | |  | |
Intercom                          | Vulnerable     | `Uh oh. That page doesn't exist.`                                         |  | [Help center](https://www.intercom.com/help/)
JetBrains                       | Vulnerable     | `is not a registered InCloud YouTrack`                                  | | [YouTrack InCloud Help Page](https://www.jetbrains.com/help/youtrack/incloud/Domain-Settings.html)
Key CDN                             | Not vulnerable     | |  |
Kinsta                           | Vulnerable     | `No Site For Domain`                                                 | | [kinsta-add-domain](https://kinsta.com/knowledgebase/add-domain/)
Landingi  | Edge case     | `It looks like you’re lost...` | 
LaunchRock                         | Vulnerable     | `It looks like you may have taken a wrong turn somewhere. Don't worry...it happens to all of us.`                                                 | | 
Mashery                           | Edge Case | `Unrecognized domain`                                                   | [HackerOne #275714](https://hackerone.com/reports/275714)
Mailchimp  | Not Vulnerable |`We can't find that page It looks like you're trying to reach a page that was built by Mailchimp but is no longer active.` |
Microsoft Azure           | Vulnerable     |  |  |
Netlify | Edge Case | `Not Found - Request ID:`  |  |
Ngrok | Vulnerable | `Tunnel *.ngrok.io not found` |  | [Ngrok Documentation](https://ngrok.com/docs#http-custom-domains)
Pantheon                           | Vulnerable     | `404 error unknown site!`                                                 | | [Pantheon-Sub-takeover](https://medium.com/@hussain_0x3c/hostile-subdomain-takeover-using-pantheon-ebf4ab813111)
Pingdom | Vulnerable | `Sorry, couldn't find the status page` |  | [Support Page](https://help.pingdom.com/hc/en-us/articles/205386171-Public-Status-Page)
Readme.io | Vulnerable | `Project doesnt exist... yet!` | 
Sendgrid                         | Not vulnerable |                                                                         |
Shopify                           | Edge Case     | `Sorry, this shop is currently unavailable.`                            || [Medium Article](https://medium.com/@thebuckhacker/how-to-do-55-000-subdomain-takeover-in-a-blink-of-an-eye-a94954c3fc75) 
Short.io | Vulnerable| `Link does not exist` | 
SmartJobBoard | Vulnerable | `This job board website is either expired or its domain name is invalid.` |  | [Support Page](https://help.smartjobboard.com/en/articles/1269655-connecting-a-custom-domain-name)
Smartling| Edge Case|`Domain is not configured`  | 
Squarespace                   | Not vulnerable |                                                                         |
Statuspage | Not Vulnerable | `Status page pushed a DNS verification in order to prevent malicious takeovers what they mentioned in` [This Doc](https://support.atlassian.com/statuspage/docs/configure-your-dns/) | | [Statuspage documentation](https://help.statuspage.io/knowledge_base/topics/domain-ownership) |          
Strikingly                           | Vulnerable     | `page not found`                                                 | | [Strikingly-Sub-takeover](https://medium.com/@sherif0x00/takeover-subdomains-pointing-to-strikingly-5e67df80cdfd)
Surge.sh                         | Vulnerable     | `project not found`                                                     || [Surge Documentation](https://surge.sh/help/adding-a-custom-domain)
SurveySparrow | Vulnerable | 'Ouch! Account not found' |  |[Custom domain]( https://help.surveysparrow.com/custom-domain)
Tumblr                             | Edge Case     | `Whatever you were looking for doesn't currently exist at this address` |  | [Tumblr Custom Domains](https://www.tumblr.com/docs/en/custom_domains)
Tilda                               | Edge Case | `Please renew your subscription`                                        | 
Uberflip | Vulnerable | `Non-hub domain, The URL you've accessed does not provide a hub.` |  | [Uberflip Documentation](https://help.uberflip.com/hc/en-us/articles/360018786372-Custom-Domain-Set-up-Your-Hub-on-a-Subdomain)
Unbounce                         | Not Vulnerable | `The requested URL was not found on this server.`                       | 
Uptimerobot                           | Vulnerable     | `page not found`                                                 | | [Uptimerobot-Sub-takeover](https://exploit.linuxsec.org/uptimerobot-com-custom-domain-subdomain-takeover/)
UserVoice                       | Vulnerable     | `This UserVoice subdomain is currently available!`                      |
Vercel| Not Vulnerable| The deployment could not be found on Vercel.` |
Webflow                           | Edge Case     | `The page you are looking for doesn't exist or has been moved.` | |[forum webflow](https://forum.webflow.com/t/hosting-a-subdomain-on-webflow/59201)
Weebly                           | Vulnerable     | `Error - Page Not Found` |[Issue #1](https://github.com/the-valluvarsploit/CAN-I-TAKEOVER-XYZ-V3/issues/1)|
Wix                           | Edge Case     | `Looks Like This Domain Isn't Connected To A Website Yet!` | 
Wordpress                       | Vulnerable     | `Do you want to register *.wordpress.com?`                              | |
Worksites | Vulnerable | `Hello! Sorry, but the website you&rsquo;re looking for doesn&rsquo;t exist.` |  | 
WP Engine                       | Not vulnerable |                                                                         |
Zendesk                           | Not vulnerable     | `Help Center Closed`                                                    |  | [Zendesk Support](https://support.zendesk.com/hc/en-us/articles/203664356-Changing-the-address-of-your-Help-Center-subdomain-host-mapping-)
