### Parse JSON
['jq' - GitHub pre-built binaries ](https://github.com/stedolan/jq/releases) ---  [jq man page](https://github.com/stedolan/jq/blob/master/docs/content/manual/v1.6/manual.yml) <br>
Pipe output to 'jq' to grab specific elements/nodes

Example: grab one key from each record in JSON string ("url" field)
```jq .url```

### Pretty-print JSON
Pipe output to ```python -m jsontool``` <br>
Pipe output to ```jq```  (pretty colors, not just formatting of a single giant string)
