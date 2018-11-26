ACTIVE
======
nmap, of course
best to run inside Metasploit, even if you use no other feature of that tool
because it makes searching so easy


### For local networks
####netdiscover - very fast, uses arp; output = IP, MAC, HW Manuf based on MAC
```sudo netdiscover -P -N -L -r 192.168.1.0/24```

####nbtscan - find SMB shares/chatty windoze boxes
```nbtscan 192.168.10.2-9; nbtscan 192.168.20.2-9```

####smbmap - SMB share enumerator
```
smbmap -u admin -p admin -H $SERVER -x 'net group "Domain Admins" /domain'
smbmap -H $SERVER
```

####smbclient - connect to SMB shares to pull/put files
```smbclient -d2 -N -U guest //192.168.10.4/Public```




Passive
=======
### [Aquatone](https://github.com/michenriksen/aquatone/releases) -- excellent tool for multiple stages of bounty hunting/recon

aquatone-discover --threads 15 --nameservers 8.8.8.8 <domain>


### [SSL Transparency Report - search by host/domain](https://transparencyreport.google.com/https/certificates) -- check the hostnames that a company has registered certs for (even expired certs!), and include subdomains in search
