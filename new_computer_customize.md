Checklist for customizing a new computer
========================================

General
---------
### Settings


#### Touchpad
- enable palm protection (so mouse movements won't be detected while you're trying to type
- disable "natural" scrolling
- enable two-finger scrolling
- set triple-tap == middle mouse button == paste (in Terminal)


### Misc
- Setup printers
- Put a clock in upper right, in 12h format, include MM/DD


### Apps
- f.lux - to nix that bright white/blue screen
- install Firefox and set as default browser; follow settings in [Apps/Firefox.md]
- git & clone this wiki




Linux
------

### Settings
Run ```sudo software-properties-gtk```  (sw settings seems to be gone from config settings UI)
- Ubuntu: choose faster/fastest mirror;  "Download from"
- Ubuntu: change software settings so new versions are checked monthly
- Any: configure various Bash customizations
- Ubuntu: clock; Settings -->Details-->Date & Time-->Time Format: AM/PM

#### Disable for privacy
- Disable sending any data to Canonical
- remove "Activity Monitor" (manager?) which tracks everything you do
- remove Amazon app

### Admin
- Ubuntu: upgrade to newest version via ```sudo do-release-upgrade ```
- Ubuntu: post-upgrade, re-enable 3rd party sw sources
  - Ex: file:/var/opt/amdgpu-pro-local 
http://dl.google.com/linux/chrome/deb stable                                                                                                                      
http://dell.archive.canonical.com/updates xenial-dell                                                                                                          
http://dell.archive.canonical.com/updates xenial-dell-service                                                                                                   
http://dell.archive.canonical.com/updates xenial-dell-whitehaven                                                                                               
- Ubuntu: configure LivePatch (requires UbuntuOne acct) for autoupdates of most kernel patches w/o reboot reqd



