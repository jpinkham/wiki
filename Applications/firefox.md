Plugins
-------



Plugins to add functionality
-----------------------------
|Plugin Name|URL|Description| Why |
|-----------|---|-----------|-----|
| Diigo | https://addons.mozilla.org/en-US/firefox/addon/diigo-web-collector/ | Bookmarks, annotations, oraganize research | Research |
| Auto reload Tab | https://addons.mozilla.org/en-US/firefox/addon/auto-reload-tab/ | Enable on a per-tab basis, each with custom time limit. |
| Evernote page clipper | https://addons.mozilla.org/en-US/firefox/addon/evernote-web-clipper/ | PDFs are broken! But it does clip webpages and can strip out all the ads and sidenav and whatnot | Research |
| Cookie Manager | xxxxx | Supports containers | Privacy, Security |
| I Don't Care About Cookies | xxxxx | Auto-clicks those annoying "HEY WE USE COOKIES! READ ALL ABOUT IT!" popups | Remove annoyance |
| Multi-Account Containers | https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/ | Sep cookie jars so Amazon, FB, Google, etc can't follow you all around the internet. Also allows multiple accounts logged into same service (ex: gmail). | Privacy, Security |
| Auto-delete cookies | https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/ | Delete cookies for a site, and all its trackers, when you close a tab or navigate to new site/domain. | Privacy |
| DuckDuckGo Privacy Essentials | https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/ | Forces HTTPS, blocks most trackers. | Privacy, Security |
| LastPass Password Manager | https://addons.mozilla.org/en-US/firefox/addon/lastpass-password-manager/ | Password storage, form fills, and more | Security |



Config settings to enable/customize
-----------------------------------

```
network.IDN_show_punycode = true
```
So you can't be fooled by phishing sites that are using non-ASCII characters in order to -look- like they are a legitimate site.

Resources:

* [Phishing with Unicode Domains](https://www.xudongz.com/blog/2017/idn-phishing/)

* [Threat Announcement: Phishing Sites Detected on Emoji Domains](https://info.phishlabs.com/blog/threat-announcement-phishing-sites-detected-on-emoji-domains)

* [Mozilla KB: network.IDN_show_punycode](http://kb.mozillazine.org/Network.IDN_show_punycode)
	

---

```security.webauth.u2f = true```

To enable support for U2F hardware key authentication (Ex: Yubikey)

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

