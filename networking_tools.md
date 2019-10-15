# curl

## Reading credentials from a file

Why? Because you don't want to expose sensitive data by specifying a password on the command line!

```text
-n, --netrc
```

Makes curl scan the .netrc (_netrc on Windows) file in the user's home directory for login name and password. This is typically used for FTP on Unix. If used with HTTP, curl will enable user authentication. See netrc(5) ftp(1) for details on the file format. Curl will not complain if that file doesn't have the right permissions (it should not be either world- or group-readable). The environment variable "HOME" is used to find the home directory.

```
--netrc-file <filename>
```
To point to a file other than .netrc

Credential file format:
```
machine <host>
login <username>
password <password>
```

## Submitting sensitive form data

```text
-d --data
Put all form data into a local file and use "curl -d "@<local filename>" 
		If you start the data with the letter ```@```, the rest should be a file name to read the data from, or ```-``` if you want curl to read the data from stdin. Multiple files can also be specified. Posting data from a file named ```'foobar'``` would thus be done with ```-d, --data @foobar```. When ```--data``` is told to read from a file like that, carriage returns and newlines will be stripped out.
		
```
Reference: <https://curl.haxx.se/docs/manpage.html#-d> 



## Test HTTP Response headers

`curl -I <URL>` which uses the `HEAD` HTTP method

Optionally, add `-k` if the server has a bad SSL cert

## Add custom request headers

`curl -H "<header name>:<header value>"`

## Examples

```text
<<insert curl examples here >>
```

## IPv6 disable

```text
sudo sysctl -w net.ipv6.conf.all.disable_ipv6=1
sudo sysctl -w net.ipv6.conf.default.disable_ipv6=1
```

To re-enable, run the same commands but set values above to 0

## arp tools - network discovery

Should be installed already

```text
sudo arp-scan --localnet --random --numeric
```

Better results & faster; must install first

```text
sudo netdiscover  -P -N -L -r 192.168.1.0/24
```

## avahi - network discovery/advertise

Install `avahi-utils` Finds all sort of interesting things \(primary use is Apple Bonjour\): `avahi-browse -a`

## dig

`dig @8.8.8.8 google.com +all +dnssec +trace any`

WARN: Google is one of the only nameservers that will honor the "any" flag

## netstat

### routing table

```text
netstat -ar
```

### ports listening

```text
# TCP and UDP only
netstat -at -f inet

# same, but shows numeric hosts and ports
netstat -ant -f inet  

# Shows the process listening on the port
sudo netstat -antp
```

## ufw - Uncomplicated FireWall

```text
ufw enable
ufw disable
ufw status
ufw allow <port # | service name>
```

## SSL / TLS

```text
openssl s_client -showcerts -connect <hostname>:443
sslscan <hostname>

testssl.sh https://<hostname>/[/optional/path]
My most common parameters:
testssl.sh --protocols --server-defaults --server-preference



nmap --script "ssl*" -p 443 <hostname>
```

