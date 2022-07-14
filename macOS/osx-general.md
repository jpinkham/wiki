# osx

## Command line

### Processes

#### Disable Spotlight indexing because it steals all your damn CPU cycles
`sudo mdutil -a -i off`

### CPU info, detailed
```
sysctl -a
```


### Disk-related

#### Show the total size of the current directory \(and all its subdirs\)

`du -c -h -s`  
-c = grand total for all files  
-h = human-readable \(KB, MB, GB, etc\)  
-s = summarize = display only a total

#### Mounting an NTFS drive as read-write

`sudo mount -v -t ntfs -o rw,auto,nobrowse /dev/disk3s1 /Volumes/Passport/`

#### List all visible disks

```text
diskutil list
```

#### Zeroing out a disk \(safer than just formatting\)

```text
diskutil zeroDisk /dev/disk4
```

### Misc

#### Location of iCloud Drive:

`~/Library/Mobile\ Documents/com~apple~CloudDocs/` Use this for command line access to pull/push files like any other directory. OSX will take care of getting it uploaded to iCloud.

#### Creating app-specific passwords when you have 2FA enabled

Ex usage: accessing an iCloud calendar with Amazon Alexa  
Log on to [https://appleid.apple.com/](https://appleid.apple.com/). Navigate to Security --&gt; App-specific Passwords --&gt; Generate  
You may want to take a screenshot of the password that gets generated because you will never be able to see it again

#### Change a user's default shell

`sudo chsh -s /path/to/shell username`

Source: [https://superuser.com/questions/379725/how-do-i-change-a-users-default-shell-in-osx](https://superuser.com/questions/379725/how-do-i-change-a-users-default-shell-in-osx)

#### Add user to a group

`sudo dscl . append /Groups/wheel GroupMembership $USER`
will add current user to "wheel" group

### Homebrew - installer for all the good stuff

* Install packages: `brew install <package>`
* Search for specific packages: `brew search [--desc] <search term or regex>`  

```text
    Use ```--desc``` to search package description (and include in output), not just package title
```

* Upgrade packages: `brew upgrade`
* Upgrade one package: `brew upgrade <package>`
* Getting help for any brew command: `brew help <command>`

More brew documentation available at [https://docs.brew.sh](https://docs.brew.sh)

#### launchctl - Launch Control

Start, stop, enable, disable, unload from memory

**See what services may be running**

Just apple, or everything but apple

```text
launchctl list |awk {'print $3'}|sort|grep apple
launchctl list |awk {'print $3'}|sort|grep -v apple
```

**Turn off Symantec virus scanner until next reboot**

```text
launchctl stop com.symantec.uiagent.application.NFM
launchctl remove com.symantec.uiagent.application.NFM
```

### Command line tools I should research further

#### ioreg - displays the I/O Kit registry.  It shows the hierarchical registry structure as an inverted tree.

#### spctl - manages the security assessment policy subsystem.

Whatever that means.

```text
You can checked whether user consent is enabled in general the following command:

spctl kext-consent status 

The result should be 

Kernel Extension User Consent: ENABLED

This can be done by a normal user and does not require sudo or booting in recovery mode. Note to make modifications, you have to boot into recovery mode, but the check can be done from a normally booted machine.
```

#### kextstat -- display status of loaded kernel extensions \(kexts\)

```text
You can checked to see if the kext has been loaded using the command:

kextstat | grep silabs

This is an example showing the CP210xVCPDriver loaded:

  188    0 0xffffff7f83b8e000 0x9000     0x9000     com.silabs.driver.CP210xVCPDriver (5.0.5) AB2A33AD-B60D-35F9-A3F5-084252A66E50 <145 22 4 3>

Another useful command is

kextfind /Library/Extensions -loaded

This can show you the current user-approved extensions in case you want to look for potential conflicts.
```

Reference: Mentioned in [https://www.silabs.com/community/interface/knowledge-base.entry.html/2018/03/30/usb\_to\_uart\_bridgev-Dnef](https://www.silabs.com/community/interface/knowledge-base.entry.html/2018/03/30/usb_to_uart_bridgev-Dnef)

“Use your macOS terminal shell to do awesome things”. [https://github.com/herrbischoff/awesome-macos-command-line](https://github.com/herrbischoff/awesome-macos-command-line)

### dtruss - strace-ish tool
If you need to snoop on the activities of a command line tool, run ```dtruss <app> <app arguments>```

Other tools are available from the DTrace package: execsnoop, iosnoop, iotop, opensnoop, rwsnoop, etc

## OS X UI

### Finder

#### Show/Hide hidden files
Shift + Cmd + .

#### Permanent delete one or more files

Option + Cmd + Delete

#### Empty trash

Shift + Cmd + Delete

### System Preferences

#### Fix scrolling so it's correct \(to me\) and apparently unnatural \(to Apple fans\)

Trackpad --&gt; Scroll & Zoom --&gt; UNcheck "Scroll direction: Natural"

#### Enable SSH server

Sharing --&gt; Remote login

