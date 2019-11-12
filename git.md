# git

\[ \] TODO: Merge resolution

### Cloning a repo, in case I get a head injury and forget how to do this

`git clone <ssh or HTTPS url> [local_name_to_use]`

### Looking at diffs of actual changes, while viewing logs

```
git log -U
git log --color --patch --no-merges --ignore-all-space --unified=1
```
Colored, include associated diff/patch, ignore whitespace changes and all merges, provide just 1 line of context near the changes

### Creating a new branch based off the current branch

`git checkout -b <new branch name>`

### List of branches you've ever checked out in this repo

`git branch`

### Grepping files in the repo

`git grep <grep options> [file path/pattern]`

### Checking out code from a specific pull request

```text
1. Clone the repo
2. Fetch the pull request and store in a custom branch
git fetch origin pull/ + PR number + /head: + custom branch name
3. Checkout the custom branch
```
Reference: https://help.github.com/en/articles/checking-out-pull-requests-locally 



### Determine what files changed, excluding deleted

Reasoning: for doing secure code reviews on a diff with thousands of files. Goal was to exclude all changes but additions and modifications, as well as filter result through grep in order to ignore different file extensions

`git diff --ignore-all-space --name-status --diff-filter=AM <branch/tag to compare> | grep -vE 'test|properties|config|gradle|\.xml|\.txt|Impl|nterfaces?'  >  <path to file to store output>`

`--name-status` prepends a single letter to each changed file, denoting if new (A), modified (M), Deleted (D), etc`
`

Reference: https://git-scm.com/docs/git-diff#Documentation/git-diff.txt---diff-filterACDMRTUXB82308203

--

## Global git settings

### Show all global variables

`git config --list`

### Set or change the fullname or email address used in your commits

```text
git config --global user.name "Jane Doe"
git config --global user.email janedoe@example.com
```

