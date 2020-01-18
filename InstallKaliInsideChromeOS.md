# How to install a Kali container in your Chromebook

## Use LXC to pull the latest container and start it up
```
lxc launch images:kali <your custom name>
```

## Get a shell!

```
lxc exec <your custom kali name> -- /bin/bash
```

## Replace the default debian container with kali
```
lxc rename penguin <new penguin name>
lxc rename <your custom kali name> penguin
```


References:

* https://blog.simos.info/using-the-lxd-kali-container-image/
* https://www.maketecheasier.com/run-ubuntu-container-chrome-os/
