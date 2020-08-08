# Sed and Awk one-liners

Convert Windows line endings to Unix:
```sed 's/^M$//'```


Remove leading whitespace from each line:
```sed 's/^[ \t]*//'```

Replace all occurrences of "foo" with "bar
```sed 's/foo/bar/g'```

