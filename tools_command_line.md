# tools\_command\_line

## Parse JSON

['jq' - GitHub pre-built binaries ](https://github.com/stedolan/jq/releases) --- [jq man page](https://github.com/stedolan/jq/blob/master/docs/content/manual/v1.6/manual.yml)  
Pipe output to 'jq' to grab specific elements/nodes

Example: grab one key from each record in JSON string \("url" field\) `jq .url`

## Pretty-print JSON

Pipe output to `python -m jsontool`  
Pipe output to `jq` \(pretty colors, not just formatting of a single giant string\)


## SQLite databases

Commands to poke around a db:
```
sqlite3 <path to db file>

.help - list of commands

.tables - list all tables in the db

.dump <table> - show the "CREATE TABLE" commands used to build (incl schema) 
plus full contents of table


.quit - exit
```
