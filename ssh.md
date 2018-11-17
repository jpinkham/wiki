sshd server
===========



ssh client
==========

## Config file
$HOME/.ssh/config

### Example entries
```
host server.org 
	port 12345

host bugsbunny
	IdentityFile /Users/jpinkham/.ssh/id_ecdsa
	PreferredAuthentications publickey

host github.com
	IdentityFile /Users/jpinkham/.ssh/id_github_rsa
  PreferredAuthentications publickey
```
