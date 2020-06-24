# Creating a personal DNS server with ad blocking and encrypted queries

1. Install and configure Pi-Hole on a Raspberry Pi (or any other computer)
2. Configure this adblock list for Pi-Hole: https://raw.githubusercontent.com/notracking/hosts-blocklists/master/dnscrypt-proxy/dnscrypt-proxy.blacklist.txt
3. Install dnscrypt-proxy client on Pi-Hole server
4. Set Pi-Hole upstream DNS to use local dnscrypt-proxy
5. Profit!


## Pihole settings

Settings --> DNS : tells PiHole to use dnscrypt-proxy as upstream, so only encrypted DNS queries are used over WAN

Settings --> API/Web Interface --> CPU Temperature Unit : set temp to use Farenheit


## Pihole stats
```echo ">stats" | nc localhost 4711  ```

## Pihole config files

### /etc/pihole/pihole-FTL.conf
```
ANALYZE_ONLY_A_AND_AAAA=true
AAAA_QUERY_ANALYSIS=true
RESOLVE_IPV6=false

PRIVACYLEVEL=0
```

### /etc/pihole/setupVars.conf
WARN: this should rarely need to be modified by hand, it's usually generated from values set in Admin Console

Things I had to set manually, since they changed after the initial install
```
PIHOLE_INTERFACE=eth0
IPV4_ADDRESS=192.168.11.10/16
WEBPASSWORD=      #leave this empty if you don't care about password protection for admin console
```
