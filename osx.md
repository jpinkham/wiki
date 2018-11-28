# Command line

## Show the total size of the current directory (and all its subdirs)
```du -c -h -s```
-c = grand total for all files
-h = human-readable (KB, MB, GB, etc)
-s = summarize = display only a total


## Mounting an NTFS drive as read-write
```sudo mount -v -t ntfs -o rw,auto,nobrowse /dev/disk3s1 /Volumes/Passport/```


### List all visible disks 
```
diskutil list
```

### Zeroing out a disk (safer than just formatting)
```
diskutil zeroDisk /dev/disk4
```

---


## Homebrew - installer for all the good stuff
* Install packages: ```brew install <package>```
* Search for specific packages: ```brew search [--desc] <search term or regex>```<br>
        Use ```--desc``` to search package description (and include in output), not just package title
* Upgrade packages: ```brew upgrade```
* Upgrade one package: ```brew upgrade <package>```
* Getting help for any brew command: ```brew help <command>```

More brew documentation available at https://docs.brew.sh

---

## launchctl - Launch Control
Start, stop, enable, disable, unload from memory


### Turn off Symantec virus scanner until next reboot
```
launchctl stop com.symantec.uiagent.application.NFM
launchctl remove com.symantec.uiagent.application.NFM
```

---

## Finder

### Permanent delete one or more files
Option + Cmd + Delete

### Empty trash
Shift + Cmd + Delete


---

## System Preferences

### Fix scrolling so it's correct and apparently unnatural
Trackpad --> Scroll & Zoom --> UNcheck "Scroll direction: Natural"

### Enable SSH server
Sharing --> Remote login


