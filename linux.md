### Determine kernel version
```
uname -a
```

### Determine the linux distro and version
```
cat /etc/issue
cat /etc/os-release
cat /proc/version

lsb_release -a
```
Also:
a] /etc/*-release file.

d] hostnamectl command

Source: https://www.cyberciti.biz/faq/find-linux-distribution-name-version-number/


### Display BIOS metadata -- no reboot needed! 
```sudo dmidecode --type bios```


### Ubuntu (any Debian?) -- check for non-LTS OS upgrades
```sudo vi /etc/update-manager/release-upgrades```
Make sure the "Prompt" value is set to "normal" and not "lts"

### Determine files within/installed by a package
```
apt-file list <package>   #NOTE: This works on any pkg, not just installed ones
dpkg -L <package>
```

---

### LivePatch

#### Display current config settings
```
sudo canonical-livepatch config
```

WARN: livepatch is an Ubuntu-specific thing IIRC that isn't a standard of any sort.
ALSO: multiple reports i found online, and tested myself, that report significant performance degradation in applications installed with this method.


#### Configure LivePatch check interval/frequency
```
sudo canonical-livepatch config check-interval=<number of minutes>
```
---

### Show the total size of the current directory (and all its subdirs)
```
sudo du --total --summarize --human-readable
```
NOTE: This may not work in BSD/OSX. This is equivalent and should work everywhere
```
sudo du -c -s -h
```

### Determine locations of superblock backups
```sudo mke2fs -n /dev/sda1```

Reference: https://linuxroutes.com/resolve-bad-magic-number-in-super-block-in-error/

Needed to resolve "bad magic number in super-block" error


### Mount a raid 1 (mirror) drive
```
sudo mdadm --assemble --run /dev/md0 /dev/<partition to be mounted>
Then mount /dev/md0
```
Reference: https://serverfault.com/questions/383362/mount-unknown-filesystem-type-linux-raid-member



### Show only hardware local mounted drives
```mount | grep -e '^\/dev'```
This will limit the output to lines that start with "/dev", to cut down on noise from tmpfs, sysfs, proc, snaps, etc


### Change a user's default shell
```sudo chsh -s /path/to/shell username```

Source: https://superuser.com/questions/379725/how-do-i-change-a-users-default-shell-in-osx
