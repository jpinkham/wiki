# Sed and Awk one-liners

### Convert Windows line endings to Unix:
```sed 's/^M$//'```


### Remove leading whitespace from each line:
```sed 's/^[ \t]*//'```

### Replace all occurrences of "foo" with "bar
```sed 's/foo/bar/g'```


#### Bash for loop to replace text within multiple files at once

Example:

  ```for file in `git grep -l doouble`; do sed -i 's/douuble/double/g' $file;done```

Replace ```git grep -l doouble``` with any command that returns filenames
