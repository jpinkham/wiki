## Extensions 

Not to be confused with plugins. Those are video/audio codecs, flash support, etc.

| Extension Name | URL | Description | Why |
| :--- | :--- | :--- | :--- |
| Diigo | [https://addons.mozilla.org/en-US/firefox/addon/diigo-web-collector/](https://addons.mozilla.org/en-US/firefox/addon/diigo-web-collector/) | Bookmarks, annotations, organize research | Research |
| Auto reload Tab | [https://addons.mozilla.org/en-US/firefox/addon/auto-reload-tab/](https://addons.mozilla.org/en-US/firefox/addon/auto-reload-tab/) | Enable on a per-tab basis, each with custom time limit. | Ease of use |
| Evernote page clipper | [https://addons.mozilla.org/en-US/firefox/addon/evernote-web-clipper/](https://addons.mozilla.org/en-US/firefox/addon/evernote-web-clipper/) | PDFs are broken! But it does clip webpages and can strip out all the ads and sidenav and whatnot | Research |
| Cookie Manager | [https://addons.mozilla.org/en-US/firefox/addon/a-cookie-manager/](https://addons.mozilla.org/en-US/firefox/addon/a-cookie-manager/) | Easily search, review, modify, remove cookies. Container support. Handy for nuking pesky Google ReCaptcha cookie after you fail. | Privacy, Security |
| I Don't Care About Cookies | [https://addons.mozilla.org/en-US/firefox/addon/i-dont-care-about-cookies/](https://addons.mozilla.org/en-US/firefox/addon/i-dont-care-about-cookies/) | Auto-clicks those annoying "HEY WE USE COOKIES! READ ALL ABOUT IT!" popups caused by GDPR | Ease of use |
| Multi-Account Containers | [https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/) | Sep cookie jars so Amazon, FB, Google, etc can't follow you all around the internet. Also allows multiple accounts logged into same service \(ex: gmail\). | Privacy, Recon, Security |
| Cookie AutoDelete | [https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/](https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/) | Delete cookies for a site, and all its trackers, when you close a tab or navigate to new site/domain. | Privacy |
| DuckDuckGo Privacy Essentials | [https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/](https://addons.mozilla.org/en-US/firefox/addon/duckduckgo-for-firefox/) | Forces HTTPS, blocks most trackers. | Browser speed, Privacy, Security |
| LastPass Password Manager | [https://addons.mozilla.org/en-US/firefox/addon/lastpass-password-manager/](https://addons.mozilla.org/en-US/firefox/addon/lastpass-password-manager/) | Password storage, form fills, and more | Ease of use, Security |
| Skip Redirect | [https://addons.mozilla.org/en-US/firefox/addon/skip-redirect/](https://addons.mozilla.org/en-US/firefox/addon/skip-redirect/) | Skips any intermediate pages, like trackers, affiliates, etc, sending you straight to destination | Privacy, Security |
| uBlock Origin | [https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) | Blocks ads, trackers, hosts, anything you can write a regex for.  Light on memory and high in performance \(vs AdBlock Plus\) | Browser speed, Privacy, Security |
| Tab Session Manager | [https://addons.mozilla.org/en-US/firefox/addon/tab-session-manager/](https://addons.mozilla.org/en-US/firefox/addon/tab-session-manager/) | Backup all open windows and tabs automatically. Easily recover from crashes or windows you closed accidentally. | Ease of use |
| IP Address & Domain Information | [https://addons.mozilla.org/en-US/firefox/addon/ip-address-and-domain-info/](https://addons.mozilla.org/en-US/firefox/addon/ip-address-and-domain-info/) | Lookup info about the DNS and IP address of the site you're visiting, or any other | Recon |
| NoScript Security Suite | [https://addons.mozilla.org/en-US/firefox/addon/noscript/](https://addons.mozilla.org/en-US/firefox/addon/noscript/) | Protects you from multiple JS attack vectors like XSS and Clickjacking and many others | Security |
| Privacy Badger | [https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17/](https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17/) | Created by EFF to block page and link trackers; learns as you browse | Privacy |
| Link Gopher | [https://addons.mozilla.org/en-US/firefox/addon/link-gopher/](https://addons.mozilla.org/en-US/firefox/addon/link-gopher/) | Extracts all links on a page into a new HTML file you can save | Tool |
| Ad Blocker for YouTube | [https://addons.mozilla.org/en-US/firefox/addon/adblock-for-youtube/](https://addons.mozilla.org/en-US/firefox/addon/adblock-for-youtube/) | Removes ads in the page AND in videos | Browser speed |


---

### DEBUG extensions!

```about:addons```

Click gear/cog icon and choose "Debug Add-ons"

Shortcut:
```text
about:debugging#/runtime/this-firefox
```



* Find the extension to troubleshoot/debug and click "Inspect"

  * This will open a special Developer Tools window, to the Network tab, so you can watch all interactions!
  * Example: ```about:devtools-toolbox?type=extension&id=support%40lastpass.com``` -- LastPass
  * Example: ```about:devtools-toolbox?type=extension&id=uBlock0%40raymondhill.net``` -- uBlockOrigin

  * All the usual Dev Tools functions are available
    * Use "Inspector" tab to see the source of whatever javascript is loaded by the extension
    * Use "Storage" tab to checkout the cookies, local storage, etc 
    * Use "Console" for troubleshooting (also available within Network view if you have Split Console enabled)
    
* Optional: Click the "Manifest URL" link to show the [manifest.json file](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json), which contains associated metadata (such as permissions used, associated keyboard shortcuts, etc)


Reference: https://developer.mozilla.org/en-US/docs/Tools/about:debugging


### See / Set all extension keyboard shortcuts

```about:addons```

Click gear/cog icon and choose "Manage Extension Shortcuts"

---

## Config settings to enable/customize

Resource: [http://kb.mozillazine.org/About:config\_entries](http://kb.mozillazine.org/About:config_entries)

### Get a list of all the config vars that you have customized

```text
about:support
```
This page will show you related env vars, file locations (like your profile!), add-ons, crash reports, experimental features enable/disable list, and more



Reference: [https://www.ghacks.net/2011/09/18/display-all-modified-firefox-preferences/](https://www.ghacks.net/2011/09/18/display-all-modified-firefox-preferences/)

### Expose phishing sites using non-ASCII characters in domain name

```text
network.IDN_show_punycode = true
```

Check these resources to see examples of domains that are impossible to identify visually as being likely phishing sites:

* [Phishing with Unicode Domains](https://www.xudongz.com/blog/2017/idn-phishing/)
* [Threat Announcement: Phishing Sites Detected on Emoji Domains](https://info.phishlabs.com/blog/threat-announcement-phishing-sites-detected-on-emoji-domains)
* [Mozilla KB: network.IDN\_show\_punycode](http://kb.mozillazine.org/Network.IDN_show_punycode)

---

### Enable U2F hardware key authentication

NOTE: This is only needed in OLDER FIREFOX VERSIONS.  Newer versions have this enabled by default.  Double check your current value

`security.webauth.u2f = true`


### Fix warnings about refusing to do automatic redirect

    accessibility.blockautorefresh = false
---

### Disable these "features" in Firefox that are invading your privacy

WARN: certain sites \(ex: ProtonMail\) may behave differently with privacy.resistFingerprinting disabled, ex: timestamps in GMT instead of your localtimezine

```text
#! SET THESE TO FALSE, UNLESS SPECIFIED OTHERWISE
app.normandy.enabled
app.shield.optoutstudies.enabled = true
browser.library.activity-stream.enabled
browser.newtabpage.activity-stream.feeds.telemetry
browser.newtabpage.activity-stream.telemetry
browser.ping-centre.telemetry
browser.send_pings
browser.urlbar.autofill.enabled            NOTE: in older version of Firefox, this is named browser.urlbar.autocomplete.enabled
datareporting.policy.dataSubmissionEnabled
datareporting.healthreport.uploadEnabled 
geo.enabled
media.peerconnection.enabled
network.dns.disableIPv6 = true
network.dns.disablePrefetch = true
privacy.resistFingerprinting
toolkit.telemetry.bhrPing.enabled
toolkit.telemetry.enabled
toolkit.telemetry.firstShutdownPing.enabled
toolkit.telemetry.shutdownPingSender.enabled
```
---

### Config via UI \(Preferences\)

* General --&gt; Startup --&gt; UNcheck "Restore previous session", if using Tab Session Manager extension.
* General --&gt; Language & Appearance --&gt; Fonts & Colors --&gt; Advanced --&gt; Minimum Font Size, set to 12pt or higher otherwise some text could be far too small on a high-res display.
* General --&gt; Browsing --&gt; UNcheck "Recommend extensions as you browse"
* Home --&gt; New Windows & Tabs --&gt; Set "Blank page" for both values
* Home --&gt; Firefox Home Content --&gt; UNcheck everything
* Search --&gt; Default search engine --&gt; UNcheck "Provide search suggestions"
* Privacy & Security --&gt; Content blocking --&gt; UNcheck everything, if using any extensions that block content \(makes for easier troubleshooting of broken pages\)
* Privacy & Security --&gt; Logins & Passwords --&gt; UNcheck "Ask to save logins and passwords for websites", if using a password manager extension
* Privacy & Security --&gt; Forms & Autofill --&gt; UNcheck "Autofill addresses", if using an extension like LastPass to fill forms
* Privacy & Security --&gt; Address Bar --&gt; UNcheck everything
* Privacy & Security --&gt; Firefox Data Collection & Use --&gt; UNcheck everything
* Privacy & Security --&gt; Deceptive Content and Dangerous Software Protection --&gt; UNcheck everything because this will just get in your way and invades your privacy

### Specifically for application security testing: remove several browser protections to make your browser vulnerable

```text
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

* [https://www.sans.org/webcasts/web-hacking-burp-suite-deep-dive-burp-suites-functionality-pen-testers-108860](https://www.sans.org/webcasts/web-hacking-burp-suite-deep-dive-burp-suites-functionality-pen-testers-108860)
* [https://aaronhorler.com/articles/firefox-privacy.html](https://aaronhorler.com/articles/firefox-privacy.html)

---
