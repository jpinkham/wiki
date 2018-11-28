### Determine the linux distro and version
```
cat /etc/issue
cat /etc/os-release
cat /proc/version

lsb_release -a
```

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
