# tools\_command\_line

# Parse JSON with jq

['jq' - GitHub pre-built binaries ](https://github.com/stedolan/jq/releases) ---  [Run jq in Docker](https://hub.docker.com/r/stedolan/jq)
[jq man page](https://github.com/stedolan/jq/blob/master/docs/content/manual/v1.6/manual.yml)  
accepts filename or STDIN ; use to grab specific elements/nodes, manipulate the data, find unique items, etc. AWESOME

## Example: grab one key from each record
`jq .url`

## Example: use select() for conditional output

output only records/objects that contain a non-NULL \"server_name" field
```
jq 'select(.server_name != null)'
```
or
```
tail -100f ssl.log|jq 'select(.server_name != null)'
```

