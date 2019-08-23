# JS prompt for dynamic bookmarks

!!WARN: If you don't already have some page, any page, loaded when you click/trigger this bookmark, it won't work. I haven't figured out why.

Ex use case: prompt user for a JIRA ticket, then load the ticket details page

```text
javascript: var ticket=prompt("ticket number?");  window.location.href="https://YOURJIRASERVER/jira/browse/" + ticket;
```

