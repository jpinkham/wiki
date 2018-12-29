### Determine the linux distro and version
```
cat /etc/issue
cat /etc/os-release
cat /proc/version

lsb_release -a
```

### Ubuntu (any Debian?) -- check for non-LTS OS upgrades
```sudo vi /etc/update-manager/release-upgrades```
Make sure the "Prompt" value is set to "normal" and not "lts"



### Determine kernel version
```
uname -a
```

### Show the total size of the current directory (and all its subdirs)
```
du --total --summarize --human-readable
```
NOTE: This may not work in BSD/OSX. This is equivalent and should work everywhere
```
du -c -s -h
```
