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

## Pihole commands

* ```pihole -c``` == Chronometer: realtime stats
* ```pihole -up``` == Update Pihole application
* ```pihole -g``` == Force manual Galaxy db update (should be automatically scheduled to update weekly)
* ```pihole -t``` == Realtime tail of pihole log, color-formatted version of /var/log/pihole.log
* ```pihole status``` == Returns status of DNS service as well as ad-blocking feature
* ```pihole restartdns``` == restart pihole-FTL and pihole services


# Query database
Reference:
* https://docs.pi-hole.net/database/ftl/


## Queries table
### Schema

|Field |	Type |	Allow NULLs |	Description |
|------|-------|--------------|-------------|
|id 	|integer |	No |	autoincrement ID for the table, only used by SQLite3|
|timestamp |	integer |	No |	Unix timestamp when this query arrived at FTLDNS (used as index)|
|type 	| integer |	No |	Type of this query (Ex: A, CNAME, MX)|
|status |	integer |	No |	How this query was handled by FTLDNS (see Supported status types below)|
|domain |	text |	No |	Requested domain|
|client |	text |	No |	Requesting client (IP address)|
|forward |	text |	Yes |	DNS host that query was forwarded to |
|additional_info |	blob |	Yes |	Data-dependent content, not often used|

### Query type values
|ID |	Query type |
|---|------------|
|1 	|A|
|2 	|AAAA|
|3 	|ANY|
|4 	|SRV|
|5 	|SOA|
|6 	|PTR|
|7 	|TXT|
|8 	|NAPTR|
|9 	|MX|
|10 	|DS|
|11 	|RRSIG|
|12 	|DNSKEY|
|13 	|NS|
|14 	|OTHER (any query type not covered elsewhere)|
|15 	|SVCB|
|16 	|HTTPS|

### Status values


|ID| 	Status| Block/Allow |		Details|
|--:|--------|------------|------------|
|0 |Unknown | 	❔ 	|Unknown status (not yet known)|
|1 |	Blocked |	❌ 	|Domain contained in gravity database|
|2 |	Allowed |	✅ 	|Forwarded|
|3 |	Allowed |	✅ 	|Known, replied to from cache|
|4 |	Blocked |	❌ 	|Domain matched by a regex blacklist filter|
|5 |	Blocked |	❌ 	|Domain contained in exact blacklist|
|6 |	Blocked |	❌ 	|By upstream server (known blocking page IP address)|
|7 |	Blocked |	❌ 	|By upstream server (0.0.0.0 or ::)|
|8 |	Blocked |	❌ 	|By upstream server (NXDOMAIN with RA bit unset)|
|9 |	Blocked |	❌ 	|Domain contained in gravity database - Blocked during deep CNAME inspection|
|10 |	Blocked |	❌ 	|Domain matched by a regex blacklist filter - Blocked during deep CNAME inspection|
|11 |	Blocked |	❌ 	|Domain contained in exact blacklist - Blocked during deep CNAME inspection|
|12 |	Allowed |	✅ 	|**Retried query**|
|13 |	Allowed |	✅ 	|Retried but ignored query (typically related to  DNSSEC validation)|
|14 |	Allowed |	✅ 	|**Already forwarded, not forwarding again**. Request was sent but hasn't received an answer|

### Example queries

* ```SELECT datetime(timestamp),domain,client FROM queries WHERE status IN( 12, 14) ORDER BY timestamp DESC LIMIT 10```
* ```SELECT COUNT(*) FROM queries WHERE status IN( 12, 14) AND timestamp > strftime('%s','2021-11-01') AND timestamp < strftime('%s','2021-11-06');```
