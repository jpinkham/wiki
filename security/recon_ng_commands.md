## Workspaces

Create a workspace: ```workspaces create <name>```

Switch to a workspace: ```workspaces select <name>```

List all: ```workspaces list```

## Stored information from database

```
Usage: show <companies|contacts|credentials|domains|hosts|leaks|locations|netblocks|ports|profiles|pushpins|repositories|vulnerabilities>

```


## Modules
WARN: No modules are installed by default

Show available modules from marketplace: ```marketplace info all``` or ```marketplace info <module name>```

Search marketplace for modules: ```marketplace search <search term>```

Install module from marketplace: ```marketplace install <path>``` where <path> is provided in marketplace info output
  
Load/Use module: ```modules load <path>```



## Options / Config settings
These are set per-context, ex: global, module-level, etc

Default global settings
```
[recon-ng][default] > options list

  Name        Current Value  Required  Description
  ----------  -------------  --------  -----------
  NAMESERVER  8.8.8.8        yes       default nameserver for the resolver mixin
  PROXY                      no        proxy server (address:port)
  THREADS     10             yes       number of threads (where applicable)
  TIMEOUT     10             yes       socket timeout (seconds)
  USER-AGENT  Recon-ng/v5    yes       user-agent string
  VERBOSITY   1              yes       verbosity level (0 = minimal, 1 = verbose, 2 = debug)
```
