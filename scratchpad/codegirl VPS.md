20190223 -- base OS reinstall - Upgraded to Ubuntu 18.04 LTS
=============================
- Create jpinkham user <br>
```adduser --home /home/jpinkham --shell /bin/bash jpinkham```

- add jpinkham to users who can sudo <br>
```adduser jpinkham sudo```

- Update all packages



TODO
====
```
[ ] Clone my dotfiles repo and start symlinking!
[x] Install snapd
  [ ] Install canonical-livepatch
    ----FAILED
[ ] SSH config
  [x] Port number
  [x] generate key for use with GitHub
    [x] add entry to ~/.ssh/config for GH with IdentityFile line
  [x] ssh-agent && ssh-add
  
  
[ ] install & config ufw
  [x] ssh port
[ ] postfix - check all past customizations
[ ] monit



```


Issues
======
- Livepatch install failed because of snapd issues:
```
jpinkham@codegirl:~$ sudo snap install canonical-livepatch
error: system does not fully support snapd: cannot mount squashfs image using "squashfs": mount:
       /tmp/sanity-mountpoint-904584303: unknown filesystem type 'squashfs'.
jpinkham@codegirl:~$ lsmod
libkmod: ERROR ../libkmod/libkmod-module.c:1657 kmod_module_new_from_loaded: could not open /proc/modules: No such file or directory
Error: could not get list of modules: No such file or directory
jpinkham@codegirl:~$ sudo lsmod
libkmod: ERROR ../libkmod/libkmod-module.c:1657 kmod_module_new_from_loaded: could not open /proc/modules: No such file or directory
Error: could not get list of modules: No such file or directory
```
