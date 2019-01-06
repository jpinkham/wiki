Extensions aka Plugins
-------
|Extension Name|URL|Description| Why |
|-----------|---|-----------|-----|
| Diigo | https://addons.mozilla.org/en-US/firefox/addon/diigo-web-collector/ | Bookmarks, annotations, oraganize research | Research |
| Auto reload Tab | https://addons.mozilla.org/en-US/firefox/addon/auto-reload-tab/ | Enable on a per-tab basis, each with custom time limit. | Ease of use |
| Evernote page clipper | https://addons.mozilla.org/en-US/firefox/addon/evernote-web-clipper/ | PDFs are broken! But it does clip webpages and can strip out all the ads and sidenav and whatnot | Research |
| Cookie Manager | https://addons.mozilla.org/en-US/firefox/addon/a-cookie-manager/ | Easily search, review, modify, remove cookies. Container support. Handy for nuking pesky Google ReCaptcha cookie after you fail. | Privacy, Security |
| I Don't Care About Cookies | https://addons.mozilla.org/en-US/firefox/addon/i-dont-care-about-cookies/ | Auto-clicks those annoying "HEY WE USE COOKIES! READ ALL ABOUT IT!" popups caused by GDPR | Ease of use |
| Multi-Account Containers | https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/ | Sep cookie jars so Amazon, FB, Google, etc can't follow you all around the internet. Also allows multiple accounts logged into same service (ex: gmail). | Privacy, Security |
| Cookie AutoDelete | https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/ | Delete cookies for a site, and all its trackers, when you close a tab or navigate to new site/domain. | Privacy |
| DuckDuckGo Privacy Essentials | https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/ | Forces HTTPS, blocks most trackers. | Browser speed, Privacy, Security |
| LastPass Password Manager | https://addons.mozilla.org/en-US/firefox/addon/lastpass-password-manager/ | Password storage, form fills, and more | Ease of use, Security |
| Skip Redirect | https://addons.mozilla.org/en-US/firefox/addon/skip-redirect/ | Skips any intermediate pages, like trackers, affiliates, etc, sending you straight to destination | Privacy, Security |
| uBlock Origin | https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/ | Blocks ads, trackers, hosts, anything you can write a regex for.  Light on memory and high in performance (vs AdBlock Plus) |  Browser speed, Privacy, Security |
| Tab Session Manager | https://addons.mozilla.org/en-US/firefox/addon/tab-session-manager/ | Backup all open windows and tabs automatically. Easily recover from crashes or windows you closed accidentally.  | Ease of use |


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
### Config via UI (Preferences)
* General --> Startup --> UNcheck "Restore previous session", if using Tab Session Manager extension.
* General --> Language & Appearance --> Fonts & Colors --> Advanced --> Minimum Font Size, set to 12pt or higher otherwise some text could be far too small on a high-res display.
* General --> Browsing --> UNcheck "Recommend extensions as you browse"
* Home --> New Windows & Tabs --> Set "Blank page" for both values
* Home --> Firefox Home Content --> UNcheck everything
* Search --> Default search engine --> UNcheck "Provide search suggestions"
* Privacy & Security --> Content blocking --> UNcheck everything, if using any extensions that block content (makes for easier troubleshooting of broken pages)
* Privacy & Security --> Logins & Passwords --> UNcheck "Ask to save logins and passwords for websites", if using a password manager extension
* Privacy & Security --> Forms & Autofill --> UNcheck "Autofill addresses", if using an extension like LastPass to fill forms
* Privacy & Security --> Address Bar --> UNcheck everything
* Privacy & Security --> Firefox Data Collection & Use --> UNcheck everything
* Privacy & Security --> Deceptive Content and Dangerous Software Protection --> UNcheck everything because this will just get in your way and invades your privacy

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

