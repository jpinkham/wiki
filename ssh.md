# ssh

## sshd server

### Set alternate port to script kiddies will leave you alone

`Port 12345`

## Determining ssh key metadata

Determining the fingerprint of an existing keyfile \(bits, key type, encryption algorithm, etc\) `ssh-keygen -l -f ~/.ssh/<file>`

Example output

```text
1024 SHA256:<my key> <username>@<hostname> (RSA)
```

## ssh key forwarding

This is a handy feature that can store keys in a cache, including passphrases. For security reasons, it's best to set short expiration times on the keys in the agent.

### Start the ssh-agent that will forward keys for you

```text
Output looks like
```

SSH\_AUTH\_SOCK=/var/folders/zv/1s20m9ld4q3f9vbc8\_p\_tqsr0000gr/T//ssh-sIqoO8v23bRX/agent.33845; export SSH\_AUTH\_SOCK; SSH\_AGENT\_PID=33846; export SSH\_AGENT\_PID; echo Agent pid 33846;

```text
### Add any keys you want into the agent
```

ssh-add -t 86400 ~/.ssh/id\_file\_to\_use \#set expire time to 1 day

```text
Output looks like
```

Enter passphrase for /your\_home\_dir/.ssh/id\_file\_to\_use: Identity added: /your\_home\_dir/.ssh/id\_file\_to\_use \(/your\_home\_dir/.ssh/id\_file\_to\_use\) Lifetime set to 86400 seconds

```text
If you see this error, something went wrong with setting the env var but it's
easy to workaround
```

Could not open a connection to your authentication agent.

```text
Find the output from the agent startup and re-run these commands
```

SSH\_AUTH\_SOCK=your\_output\_here; export SSH\_AUTH\_SOCK;

```text
and then retry the ```ssh-add``` command



ssh client
==========

## Config file
$HOME/.ssh/config

### Example entries
```

host server.org port 12345

host bugsbunny IdentityFile /Users/jpinkham/.ssh/id\_ecdsa PreferredAuthentications publickey

host github.com IdentityFile /Users/jpinkham/.ssh/id\_github\_rsa PreferredAuthentications publickey

\`\`\`

