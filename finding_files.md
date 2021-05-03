# Various methods for finding files

## List full path to files, of specific types
  * ```find / -type d -print``` (to list only directories)
  * ```find / -type l -print``` (to list only soft links)
  * ```find / -type b -print``` (to list only block special files)
  * ```find / -type f -print``` (to list only regular files)


## List ONLY symbolic links, descending only 2 dir deep
``` find . -maxdepth 2 -type l -exec ls -al "{}" \; ```

## Show only "dotfiles" in 'ls' output
Add this to your $HOME/.bashrc:
```alias dot='ls -ldF .[a-zA-Z0-9]*'```
