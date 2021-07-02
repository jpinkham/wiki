## Aliases
Create postfix email aliases in order to:
  * Have one internal user receive mail for another internal user
  * Send email to an external address

Edit the file containing the aliases:
```sudo vi /etc/aliases```

Run this command for postfix to use the updated file:
```newaliases```


Example aliases file:
```
postmaster : root
root : other.user@gmail.com
webmaster: user2
```
