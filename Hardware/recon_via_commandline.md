Once you have shell access to a device (running some form of *nix), run through these to quickly learn as much as possible

##Commands to try:

    whoami
    pwd
    ps
    cat /proc/cpuinfo || lscpu
    cat /etc/resolv.conf
    ifconfig -a
    uname -a
    date (to determine timezone as well as current date/time)
    df -h
    mount
    crontab -l
    netstat    -antp,  -ar,   - atp
    set
    printenv
    uptime
    lsblk
    lsusb
    lspci
    lshw
    ls
    lsmod
    lsof (if installed)
    hwinfo —short
    last - shows recent user logins AND reboot/shutdown/crash



## Directories of interest:
```
    /
    /bin
    /sbin
    /etc/conf.d
    /etc/init.d
    /home
    /var/run
    /usr, /usr/bin, /usr/local
    /sys/bus, /sys/devices, /sys/module
    /opt

```



## Files of interest:
```
    /proc/kmsg - looks to be boot up log of kernel modules [ likely same output as ‘dmesg']
    /proc/cmdline - looks to be options/arguments passed to kernel loader
    /proc/devices
    /proc/version - linux version and gcc compiler version
```
