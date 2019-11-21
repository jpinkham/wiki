# GitHub

## Creating/editing

### Creating a new file within a new directory

From the location where you want to create a new directory, click the "Create new file" button. In the space for the filename, enter the directory name to create, and **add a trailing slash**. You will then be presented with a blank editor for your new file. Enter the filename at the top and start editing.

If you simply want to create a new directory, you'll need to create a placeholder file to put into it, and commit it. GitHub doesn't like empty directories.

### Moving/Renaming a file

Edit the file. 

- Move to a subdirectory of the current location: prepend the filename with "/" and start typing the destination subdirectory name.

- Move to a location "above" the current location: prepend the filename with "../" and start typing the destination directory path.

- Change filename: just change the name and commit.

Demo, which explains this much better:

![demonstration](https://help.github.com/assets/images/help/repository/moving_files.gif)

Reference: [Moving a file to a new location -- GitHub Help](https://help.github.com/en/github/managing-files-in-a-repository/moving-a-file-to-a-new-location)


## Reviewing diffs


### Filter out whitespace changes

Add ```?w=1``` to the url. Should work in any type of "Compare" view.


### Expand/collapse all files at once

Hold down the Alt key and click on the inverted caret icon in _any_ file header.

After clicking the link for "files changed", you can click on any file in the list and it will auto-expand before jumping to the file.

Reference: [Collapse all diffs in a pull request at once](https://blog.github.com/changelog/2018-08-17-collapse-all-diffs-in-a-pull-request-at-once/)

