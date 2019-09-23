# ssh

## sshd server

### Set alternate port to script kiddies will leave you alone

`Port 12345`

## Determining ssh key metadata

Determining the fingerprint of an existing keyfile (bits, key type, encryption algorithm, etc)
```
ssh-keygen -l -f ~/.ssh/<file>
```

Example output

```text
1024 SHA256:<my key> <username>@<hostname> (RSA)
```

## ssh key forwarding

This is a handy feature that can store keys in a cache, including passphrases. For security reasons, it's best to set short expiration times on the keys in the agent.

### Start the ssh-agent that will forward keys for you

Output looks like

```
SSH_AUTH_SOCK=/var/folders/zv/1s20m9ld4q3f9vbc8_p_tqsr0000gr/T//ssh-Q7NiRJVvk5X4/agent.7403; export SSH_AUTH_SOCK;
SSH_AGENT_PID=7404; export SSH_AGENT_PID;
echo Agent pid 7404;
```

### Add any keys you want into the agent

```
ssh-add -t 86400 ~/.ssh/id_file_to_use #set expire time to 1 day
```

Output looks like

```
Enter passphrase for /your_home_dir/.ssh/id_file_to_use: 
Identity added: /your_home_dir/.ssh/id_file_to_use (/your_home_dir/.ssh/id_file_to_use) 
Lifetime set to 86400 seconds
```

If you see this error, something went wrong with setting the env var but it's
easy to workaround
```
Could not open a connection to your authentication agent.
```

Workaround: Find the output from the agent startup and re-run these commands
```
SSH_AUTH_SOCK=original_output_value_here; 
export SSH_AUTH_SOCK;
```

and then retry the ```ssh-add``` command



ssh client
==========

## Config file
```$HOME/.ssh/config```

### Example entries
```

# custom port
host server.org
    port 12345

# public key authentication
host github.com
   IdentityFile /Users/jpinkham/.ssh/id_github_rsa 
   PreferredAuthentications publickey

# custom port + public key authentication
host my_local_server 192.168.1.161
	port 123456
	IdentityFile /Users/jpinkham/.ssh/id_file_here
	PreferredAuthentications publickey


```
