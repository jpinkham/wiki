# Tips for ChromeOS / Chromebook

## Keyboard shortcuts

* Screenshots

```Ctrl + F5/Expose``` == Entire screen

```Ctrl + Shift + F5/Expose``` == Selected area

* Emulate keys not on keyboard

```
Use keys on top row:
F1 = search + "<--"
..
F10 = search + volume up
Delete = search + backspace
```
## Create folders in launcher
Drag one app onto another to create a new folder


## Install "Secure Shell App" extension
SSH, scp, sftp


## Using LXC commands to interact with containers
1. Start crosh
2. run ```vmc start termina```

### Container actions
* ```lxc list``` - display installed containers and their current state
* ```lxc image list``` - container image, size, description, etc


## Advanced config settings

### Change build/channel
To switch to "beta" or "developer" channels to get new features early, but sacrificing some stability

```chrome://settings/help```

### Enable Linux
Settings --> Linux --> Enable

Provides a Debian-based distro, using standard 'apt' tools


### Change Chrome download folder to be in your Google Drive
Settings --> Advanced --> Downloads --> Location


### URLs for hidden/advanced config options
```
chrome://chrom-urls - full list of supported urls

chrome://bluetooth-internals/ - advanced bluetooth details not available from Settings

chrome://components/ - most impt app to update: cros-termina

chrome://device-log/

chrome://devices

chrome://discards/ - not exactly sure what this is

chrome://drive-internals/ - Google Drive connection status, paths, event logs

chrome://flags - Enable hidden/beta features

chrome://gcm-internals/ - ??

chrome://gpu/ - detailed stats on GPU features, settings, logs, etc

chrome://inspect - Inspect pages, extensions, apps; dedicated DevTools for NodeJS

chrome://internet-config-dialog/ - shortcut to join a hidden wifi network

chrome://internet-detail-dialog/ - shortcut to proxy setting

chrome://interstitials/ - a list and example of all screens that Chrome sends you to in order to warn you before proceeding

chrome://interventions-internals/ - ?

chrome://local-state/ - JSON format of several metrics

chrome://net-export/ - Capture a network log, optionally including credentials

chrome://network/ - Visible wifi networks, plus other stuff I'm not sure what it does

chrome://omnibox/ - search box on steroids

chrome://power/ --- Battery usage graph!

chrome://predictors/ - list of predictions that Chrome will offer as you type, based on what it's learned from your browsing history

```

