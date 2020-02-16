These items may be specific to my Netgear R7800, purchased from FlashRouters.com (I bricked 2 routers and decided to stop and just buy a nice one).

Current firmware version: ```DD-WRT v3.0-r41892 std (01/05/20)``` --- installed late Jan 2020

My network setup:

```
Internet --> ISP cable modem (bridge mode) --> hardware lan tap ---> DD-WRT router WAN port
                                          lan tap monitor ports ---> SecurityOnion 2 network cards in promiscuous mode
```

Subnetting internal network: Static for everything possible, even IoT. 

Internal services:
* DD-WRT
  * DHCP
  * dnsmasq: used with DHCP to force clients to use internal DNS
* Linux servers
  * DNS server: [Pi-hole ad-blocking](pi-hole.net)


---
## Setup tab

### Basic setup tab
* WAN Connection Type: Automatic Configuration - DHCP  (Since ISP modem is in Bridge mode, we want to get a dynamic address from the ISP)
* Optional . Router Name: this name will appear when you do internal traceroute, ping, etc

* Network.Router IP: 192.168.1.1

* DHCP.Type: Authoritative

* Time.NTP Client == Enabled
* Time.Server == north-america.pool.ntp.org

### DDNS tab
Using [Cisco OpenDNS](https://signup.opendns.com/homefree/) service, mainly to track stats on requests that may have slipped past the Pi-hole internal DNS.

This was a bit of a PITA to get right.

* DDNS Service: Custom
* DynDNS Server: ```updates.dnsomatic.com```
* Hostname: ```all.dnsomatic.com```
* URL: ```https://updates.dnsomatic.com/nic/update?hostname=```


References:
* https://wiki.dd-wrt.com/wiki/index.php/OpenDNS
* https://support.opendns.com/hc/en-us/articles/227987727-Linux-IP-Updater-for-Dynamic-Networks
* https://www.dnsomatic.com/docs/api



## Services

### Services tab
DNSmasq.enabled == yup
DNSmasq.Additional Dnsmasq Options = ```dhcp-option=6,192.168.1.14``` -- Supplies internal DNS Pi-hole server as default DNS for DHCP client

References:
* https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245


### SSHd
Once enabled, make sure to use user ```root``` when connecting via SSH. DO NOT use the admin username you created during initial configuration. You WILL use the same password.
