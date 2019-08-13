# misc

Until I get enough stuff in here to further subdivide, it will all get dumped here

## UI

### To add or remove startup items

For _all_ users via the Startup folder, type the following shell command in the Run dialog:

```text
shell:Common Startup
```

For _current_ user

```text
shell:Startup
```

### Pin a window to all desktops

* Pin all current and future windows of an app
* Pin a single window of a multi-window app  \(Ex: one OneNote window when you have several open\)

Launch Task View, then right-click on the window you want to pin and choose “Show this window on all desktops”.

Reference: [https://superuser.com/questions/950960/pin-applications-to-multiple-desktops-in-windows-10](https://superuser.com/questions/950960/pin-applications-to-multiple-desktops-in-windows-10)

### Modify HOSTS file

aka /etc/hosts \(on linux\)

File location:

```text
Reference: https://www.petri.com/easily-edit-hosts-file-windows-10


# Command line

## Kill a process from the command line
1. To kill a process by its PID, type the command:
```taskkill /F /PID <pid_number>
```

1. To kill a process by its name, type the command

   `taskkill /IM "<process name>" /F`

Reference: [https://winaero.com/blog/kill-process-windows-10/](https://winaero.com/blog/kill-process-windows-10/)

### List all processes/tasks

1. CMD: `tasklist.exe`
2. PowerShell: `get-process` or `gps`

Reference: [https://www.digitalcitizen.life/how-print-list-running-processes-windows-7-windows-8](https://www.digitalcitizen.life/how-print-list-running-processes-windows-7-windows-8)

### Open a File Manager window from the command line

Use case: you've moved around in the terminal and now you want to open a File Manager window for the current directory `start .`

Reference: [https://www.howtogeek.com/howto/windows-vista/stupid-geek-tricks-open-an-explorer-window-from-the-command-prompts-current-directory/](https://www.howtogeek.com/howto/windows-vista/stupid-geek-tricks-open-an-explorer-window-from-the-command-prompts-current-directory/)

### Print system information

`systeminfo`

Example fields: OS name/version/config, system manufacturer/model, root device, windows dir, physical/virtual memory stats, Active Directory Domain, AD logon server, applied hotfixes, network interfaces

