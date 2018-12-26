Plugins to protect your privacy/increase security
=================================================
|Plugin Name|URL|Description|
|-----------|---|-----------|
|Multi-Account Containers|https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/|Sep cookie jars so Amazon, FB, Google, etc can't follow you all around the internet. Also allows multiple accounts logged into same service (ex: gmail).|
|Auto-delete cookies|https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/|Delete cookies for current site when you close a tab or navigate to new site/domain.|
|DuckDuckGo Privacy Essentials|https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/|Blocks most trackers. Grades security of pages you visit.|
|HTTPS Everywhere|https://addons.mozilla.org/en-US/firefox/addon/https-everywhere/|Force use of HTTPS for all URLs on any site you visit, it site supports HTTPS.|


Config settings to enable/customize
===================================

```
network.IDN_show_punycode = true
```
So you can't be fooled by phishing sites that are using non-ASCII characters in order to -look- like they are a legitimate site.

Resources:

* [https://www.xudongz.com/blog/2017/idn-phishing/]()

* [Threat Announcement: Phishing Sites Detected on Emoji Domains](https://info.phishlabs.com/blog/threat-announcement-phishing-sites-detected-on-emoji-domains)

* [Mozilla KB: network.IDN_show_punycode](http://kb.mozillazine.org/Network.IDN_show_punycode)
	

---
	
	security.webauth.u2f = true
To enable support for U2F hardware keys (like YubiKeys).

---
	
### Disable these "features" in Firefox that are invading your privacy

```
#! SET THESE TO FALSE, UNLESS SPECIFIED OTHERWISE
app.normandy.enabled
app.shield.optoutstudies.enabled
browser.library.activity-stream.enabled
browser.newtabpage.activity-stream.feeds.telemetry
browser.newtabpage.activity-stream.telemetry
browser.ping-centre.telemetry
browser.send_pings
browser.urlbar.autocomplete.enabled
datareporting.policy.dataSubmissionEnabled
datareporting.healthreport.uploadEnabled 
dom.event.contextmenu.enabled 
geo.enabled
media.peerconnection.enabled
network.dns.disablePrefetch = true
privacy.resistFingerprinting
toolkit.telemetry.enabled
```
	
---
	
	
### Specifically for application security testing: remove several browser protections to make your browser vulnerable

```
#! SET THESE TO FALSE, UNLESS SPECIFIED OTHERWISE
browser.safebrowsing.blockedURIs.enabled
browser.safebrowsing.downloads.enabled
browser.safebrowsing.downloads.remote.enabled
browser.safebrowsing.malware.enabled
browser.safebrowsing.phishing.enabled
browser.urlbar.filter.javascript
network.captive-portal-service.enabled
plugins.flashBlock.enabled
privacy.trackingprotection.annotate_channels
privacy.trackingprotection.pbmode.enabled
security.tls.version.min = 0
security.mixed_content.block_active_content
security.ssl.enable_ocsp_stapling
security.ssl.errorReporting.enabled
```
Resources:

* https://www.sans.org/webcasts/web-hacking-burp-suite-deep-dive-burp-suites-functionality-pen-testers-108860
* https://aaronhorler.com/articles/firefox-privacy.html

