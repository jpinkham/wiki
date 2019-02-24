TODO
====
```
[X] VM: Tails
[x] VM: Kali 2019.1
[ ] VM: FreeBSD
[ ] VM: Buscador 2.0
[ ] VM: ParrotSec
[ ] VM: Android x86
[ ] VM: Elementary OS
[ ] VM: Metasploitable
[ ] VM: Security Onion
[ ] VM: ReactOS - linux-ish distro that can run Windows binaries!!  Should run Evernote when 0.4.11 is released.
[ ] VM: Windows 7
[ ] VM: Windows 10
	[ ] WinPatrol
	[ ] iDrive
	[ ] Evernote
	[ ] Overdrive ODM (audiobooks)
	
[ ] Conky
[ ] Clonezilla - create bootable clone on 4TB drive
[X] Reconfigure LivePatch to run only once or twice per day
[ ] Install ProtonMail Bridge
[ ] Configure Evolution to work with iCloud calendar and contacts
[ ] Configure iDrive for automated backups

```

---
Daily changes
=============

### 2/24/2018
- Installed Vineyard - helper for Wine, so I can try running some Windoze apps without a VM 
- Cloned win10 VM on macbook, copied files to laptop
	* VM seems to work but it's so high res I can barely see it. 
	* Need to determine how to set a different resolution on the VM
- Installed 'pip' (apparently that doesn't come with installing python?)
- Installed pip 'bandit' (python SAST):
```
Installing collected packages: PyYAML, pbr, six, stevedore, smmap2, gitdb2, GitPython, bandit
Successfully installed GitPython-2.1.11 PyYAML-3.13 bandit-1.5.1 gitdb2-2.0.5 pbr-5.1.2 six-1.12.0 smmap2-2.0.5 stevedore-1.30.0
```
- Installed pip 'pretty-json'  (provides json.tool)
```
	Installing collected packages: Pygments, pygments-json, pretty-json
	Successfully installed Pygments-2.3.1 pretty-json-1.2.0 pygments-json-0.1
```

---

### 2/23/2019
- Created Tails LiveCD VM
- Installed CPANM (```sudo cpan install App::cpanminus```)
- Installed "gloc": Perl GNU/Linux OverDrive/eMusic Client -- downloads OverDrive books using .odm files

---

### 2/18/2019
- Installed numlockx, so I can use the numlock setting in 
		```Control Center --> Admin --> Login window --> Settings --> Activate numlock```
- Added more virtual desktops/workspaces, so I have 10 total
- Custom keyboard settings: ((Control Center --> Hardware --> Keyboard)
	- Keyboard --> Layout --> Custom model: Dell Precision M laptop (which includes sep numpad area)
	- Keyboard --> Layout --> Options --> 
		- Caps Lock Behavior --> Disable
		- Key sequence to kill the X server --> Enable: Ctrl-Alt-Backspace
- Keyboard shortcuts (Control Center --> Hardware --> Keyboard shortcuts)
	- Add shortcuts for new virtual desktop 5-10 (Ctrl + #)
	- Tile window to left side of screen = Mod4/Win + <--
	- Tile window to right side of screen = Mod4/Win + -->
	- Move window to workspace 0-9 = Ctrl + Alt + #
- Configure iDrive and run full backup (NEW! Configure and run backups from web dashboard)
	- Download latest set of scripts (https://www.idrivedownloads.com/downloads/linux/download-for-linux/IDriveForLinux.zip)
	- Unzipped to /usr/
	- Ran /usr/IDriveForLinux/scripts/account_setting.pl
	
---	

### 2/17/2018
- Buiding vbox from source for current kernel -- failed
- Pulled latest-ish virtualbox version (5.2.25) direct from their repo & it worked!
https://websiteforstudents.com/install-the-latest-virtualbox-on-ubuntu-18-04-lts/
- Installed latest vbox extension pack: https://www.virtualbox.org/wiki/Download_Old_Builds_5_2
- Added more ProtonVPN server configs
- Installed clipboard manager applet: http://tipsonubuntu.com/2018/02/18/install-copyq-clipboard-manager-3-2-ubuntu-18-0416-04/

- Virtualbox:
	- Mounted new SSD to VirtualBox\ VMs
```
sudo chmod 765 VirtualBox\ VMs/
sudo chown jpinkham.vboxusers VirtualBox\ VMs/
sudo chgrp -R vboxusers *    (in the VM dir)
```

---

### 2/14/2019
- Installed Gnome MATE properly: ```sudo apt install ubuntu-mate-desktop```
- Installed Cinnamon as well: ```sudo apt install cinnamon-desktop-environment```
Post-reboot, both showed up in the menu available at the login screen
- Installed ukuu
	- Used ukuu to install  4.20.x kernel
	- After reboot, virtualbox started up, but it complained that I needed virtualbox-dkms due to missing /dev/virtualbox or something.
- ran ```sudo apt purge virtualbox``` to remove and purge
- Reinstalled virtualbox fresh.
- Used apt to install Firefox so I won't have to use the version I downloaded from firefox that had no installer.

FRESH INSTALL DID NOT FIX VIRTUALBOX! GAH!
