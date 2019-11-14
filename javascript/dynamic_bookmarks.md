### Dynamic bookmarks
Why? I'm lazy. I want one-click access, from my browser bookmarks toolbar, to perform a search or any other action that requires dynamic data.

Basic format:
```javascript: var <custom variable name>=prompt("<text displayed in popup with text field>");  window.location.href="<static portion of url>" + <custom variable name>;```

How to use:
- Create a new bookmark, using your browser's bookmark manager
- Paste any of the examples listed below into the "URL" field
  - You must use the full string provided, including the leading ```javascript:```
  - Replace any instance of ```<some text here>``` (Ex: ```<YOUR JIRA SERVER>```) with whatever is unique about your scenario/environment, such as your JIRA server url
- Set a useful name, but keep it short to save screen real estate in your toolbar


## Tools

### Bug bounty research
- Robtex: domain name

```javascript: var domain_name=prompt("domain name to search?");  window.location.href="https://robtex.com/dns-lookup/" + domain_name;```

- Robtex: IP address

```javascript: var ip_address=prompt("IP address to search?");  window.location.href="https://robtex.com/ip-lookup/" + ip_address;```


## Apps


### JIRA ticketing system
- Search ticket title

```javascript: var searchterm=prompt("search term [ticket title search only]?"); window.location.href="https://<YOUR JIRA SERVER>/jira/issues/?jql=project%3D<PROJECT NAME HERE>%20AND%20summary%20~%20" + searchterm + "%20ORDER%20BY%20Updated%20DESC"```

- Ticket detail view

```javascript: var ticket=prompt("ticket number?");  window.location.href="https://<YOUR JIRA SERVER>/jira/browse/" + ticket;```
