JS prompt for dynamic bookmarks
-------------------------------
Ex use case: prompt user for a JIRA ticket, then load the ticket details page

```
javascript: var ticket=prompt("ticket number?");  window.location.href="https://YOURJIRASERVER/jira/browse/" + ticket;
```
