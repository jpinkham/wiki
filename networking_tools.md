## arp tools - network discovery
Should be installed already
``` 
sudo arp-scan --localnet --random --numeric 
```
Better results & faster; must install first
```
sudo netdiscover  -P -N -L -r 192.168.1.0/24
```

## dig
```dig @8.8.8.8 google.com +all +dnssec +trace any```

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
