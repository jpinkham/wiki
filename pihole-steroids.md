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
