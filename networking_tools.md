## dig
```dig @8.8.8.8 codegirl.org +all +dnssec +trace any```

WARN: Google is one of the only nameservers that will honor the "any" flag



## netstat
### routing table
```
netstat -ar
```

### ports listening
```
# TCP and UDP only
netstat -at -f inet
   
# same, but shows numeric hosts and ports
netstat -ant -f inet  
```

## ufw - Uncomplicated FireWall
```
ufw enable
ufw disable
ufw status
ufw allow <port # | service name>
```
