[ ] TODO: Merge resolution

### Cloning a repo, in case I get a head injury and forget how to do this
```git clone <ssh or HTTPS url> [local_name_to_use]```


### Looking at diffs while viewing logs
```git log -U```


### Creating a new branch based off the current branch
```git checkout -b <new branch name>```


### List of branches you've ever checked out in this repo
```git branch```


### Grepping files in the repo
```git grep <grep options> [file path/pattern]```


### Checking out code from a specific pull request
```
1. Clone the repo
2. Fetch the pull request and store in a custom branch
git fetch origin pull/ + PR number + /head: + custom branch name
3. Checkout the custom branch
```

--
## Global git settings

### Show all global variables
```git config --list```


### Set or change the fullname or email address used in your commits
```
git config --global user.name "Jane Doe"
git config --global user.email janedoe@example.com```

