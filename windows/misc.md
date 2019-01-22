Until I get enough stuff in here to further subdivide, it will all get dumped here


# UI

## Pin a window to all desktops
* Pin all current and future windows of an app
* Pin a single window of a multi-window app  (Ex: one OneNote window when you have several open)


Launch Task View, then right-click on the window you want to pin and choose “Show this window on all desktops”. 

Reference: https://superuser.com/questions/950960/pin-applications-to-multiple-desktops-in-windows-10

---

## Modify HOSTS file
aka /etc/hosts (on linux)

File location: 
```C:\Windows\System32\Drivers\etc```

Reference: https://www.petri.com/easily-edit-hosts-file-windows-10


# Command line

## Kill a process from the command line
1. To kill a process by its PID, type the command:
```taskkill /F /PID <pid_number>```
2. To kill a process by its name, type the command
```taskkill /IM "<process name>" /F```

Reference: https://winaero.com/blog/kill-process-windows-10/


---

## Open a File Manager window from the command line
Use case: you've moved around in the terminal and now you want to open a File Manager window for the current directory
```start .```

Reference: https://www.howtogeek.com/howto/windows-vista/stupid-geek-tricks-open-an-explorer-window-from-the-command-prompts-current-directory/


---

