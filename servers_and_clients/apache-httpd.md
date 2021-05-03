# Apache httpd web server

# Authentication

## Overriding authentication in a subdir

Put this in your **.htaccess** file IN the dir where you want NO authentication, when the parent dir of the dir in question DOES have authentication
```aconf
Satisfy any
```
