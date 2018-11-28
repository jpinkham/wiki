# Command line

##Show the total size of the current directory (and all its subdirs)
```du -c -h -s```
-c = grand total for all files
-h = human-readable (KB, MB, GB, etc)
-s = summarize = display only a total


## Mounting an NTFS drive as read-write
```sudo mount -v -t ntfs -o rw,auto,nobrowse /dev/disk3s1 /Volumes/Passport/```

## diskutil for all things int/ext/network disks

### Description
NAME: hdiutil -- manipulate disk images (attach, verify, create, etc)

SYNOPSIS: 
```hdiutil <verb> [options]```

DESCRIPTION
     hdiutil uses the DiskImages framework to manipulate disk images.  Common verbs include
     attach, detach, verify, create, convert, and compact.

     The rest of the verbs are currently: help, info, burn, checksum, chpass, erasekeys,
     unflatten, flatten, imageinfo, isencrypted, mountvol, unmount, plugins, udifrez,
     udifderez, internet-enable, resize, segment, makehybrid, and pmap.



### List all visible disks 
```
diskutil list
```

### Zeroing out a disk (safer than just formatting)
```
diskutil zeroDisk /dev/disk4

```

## Homebrew - installer for all the good stuff
* Upgrade packages: ```brew upgrade```
* Upgrade one package: ```brew upgrade <package>```


## launchctl - Launch Control
Start, stop, enable, disable, unload from memory


### Turn off Symantec virus scanner until next reboot
```
launchctl stop com.symantec.uiagent.application.NFM
launchctl remove com.symantec.uiagent.application.NFM
```


## Finder

### Permanent delete one or more files
Option + Cmd + Delete

### Empty trash
Shift + Cmd + Delete




## System Preferences

### Fix scrolling so it's correct and apparently unnatural
Trackpad --> Scroll & Zoom --> UNcheck "Scroll direction: Natural"

### Enable SSH server
Sharing --> Remote login


