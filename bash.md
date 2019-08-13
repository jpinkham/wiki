# All things Bash \(Bourne Again SHell\)

## Customizing prompt

### Add git info to prompt

```text
# Git command completion
source $HOME/git-completion.bash

# Prompt shows state of Git, when in repository directories
export GIT_PS1_SHOWDIRTYSTATE=1
export GIT_PS1_SHOWSTASHSTATE=1
export GIT_PS1_SHOWUNTRACKEDFILES=1
if [ "$PS1" ]; then
  if [ "$BASH" ]; then
    if [ -f /etc/bash.bashrc ]; then
        . /etc/bash.bashrc
    fi
    if [ "`id -u`" -eq 0 ]; then
       PS1='\[\033[01;31m\]\h \[\033[01;34m\]\W \$ \[\033[00m\]'
    else
       PS1='$(__git_ps1 "(%s) ")\[\033[01;32m\]\u@\h \[\033[01;34m\]\w \$ \[\033[00m\]'
    fi
  fi
fi
```

## Bash history

### Add date/time stamp to history entries

Add to ~/.bash\_profile or ~/.bashrc

```text
export HISTTIMEFORMAT="%Y-%m-%d %T "
```

Reference: [https://stackoverflow.com/questions/38526588/linux-command-history-with-date-and-time](https://stackoverflow.com/questions/38526588/linux-command-history-with-date-and-time)

