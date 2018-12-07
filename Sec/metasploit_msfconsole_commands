Core Commands
=============

    Command       Description
    -------       -----------
    ?             Help menu
    banner        Display an awesome metasploit banner
    cd            Change the current working directory
    color         Toggle color
    connect       Communicate with a host
    exit          Exit the console
    get           Gets the value of a context-specific variable
    getg          Gets the value of a global variable
    grep          Grep the output of another command
    help          Help menu
    history       Show command history
    load          Load a framework plugin
    quit          Exit the console
    repeat        Repeat a list of commands
    route         Route traffic through a session
    save          Saves the active datastores
    sessions      Dump session listings and display information about sessions
    set           Sets a context-specific variable to a value
    setg          Sets a global variable to a value
    sleep         Do nothing for the specified number of seconds
    spool         Write console output into a file as well the screen
    threads       View and manipulate background threads
    unload        Unload a framework plugin
    unset         Unsets one or more context-specific variables
    unsetg        Unsets one or more global variables
    version       Show the framework and console library version numbers


Module Commands
===============

    Command       Description
    -------       -----------
    advanced      Displays advanced options for one or more modules
    back          Move back from the current context
    info          Displays information about one or more modules
    loadpath      Searches for and loads modules from a path
    options       Displays global options or for one or more modules
    popm          Pops the latest module off the stack and makes it active
    previous      Sets the previously loaded module as the current module
    pushm         Pushes the active or list of modules onto the module stack
    reload_all    Reloads all modules from all defined module paths
    search        Searches module names and descriptions
    show          Displays modules of a given type, or all modules
    use           Selects a module by name


Job Commands
============

    Command       Description
    -------       -----------
    handler       Start a payload handler as job
    jobs          Displays and manages jobs
    kill          Kill a job
    rename_job    Rename a job


Resource Script Commands
========================

    Command       Description
    -------       -----------
    makerc        Save commands entered since start to a file
    resource      Run the commands stored in a file


Developer Commands
==================

    Command       Description
    -------       -----------
    edit          Edit the current module or a file with the preferred editor
    irb           Open an interactive Ruby shell in the current context
    log           Display framework.log paged to the end if possible
    pry           Open the Pry debugger on the current module or Framework
    reload_lib    Reload Ruby library files from specified paths


Database Backend Commands
=========================

    Command           Description
    -------           -----------
    db_connect        Connect to an existing database
    db_disconnect     Disconnect from the current database instance
    db_export         Export a file containing the contents of the database
    db_import         Import a scan result file (filetype will be auto-detected)
    db_nmap           Executes nmap and records the output automatically
    db_rebuild_cache  Rebuilds the database-stored module cache
    db_status         Show the current database status
    hosts             List all hosts in the database
    loot              List all loot in the database
    notes             List all notes in the database
    services          List all services in the database
    vulns             List all vulnerabilities in the database
    workspace         Switch between database workspaces


Credentials Backend Commands
============================

    Command       Description
    -------       -----------
    creds         List all credentials in the database

--------------------------------------------------------------

Help for core commands

msf > help get
Usage: get var1 [var2 ...]

The get command is used to get the value of one or more variables.

msf > help getg
Usage: getg var1 [var2 ...]

Exactly like get -g, get global variables

msf > help history
Usage: history [options]

Shows the command history.

If -n is not set, only the last 100 commands will be shown.
If -c is specified, the command history and history file will be cleared.

OPTIONS:

    -a        Show all commands in history.
    -c        Clear command history and history file.
    -h        Help banner.
    -n <opt>  Show the last n commands.
msf > help load
Usage: load <option> [var=val var=val ...]

Loads a plugin from the supplied path.
For a list of built-in plugins, do: load -l
The optional var=val options are custom parameters that can be passed to plugins.

msf > load -l
[*] Available Framework plugins:
    * ffautoregen
    * session_notifier
    * auto_add_route
    * wiki
    * komand
    * lab
    * event_tester
    * nessus
    * beholder
    * session_tagger
    * sample
    * nexpose
    * msgrpc
    * wmap
    * token_adduser
    * request
    * openvas
    * db_credcollect
    * pcap_log
    * aggregator
    * sqlmap
    * db_tracker
    * rssfeed
    * sounds
    * libnotify
    * alias
    * thread
    * token_hunter
    * ips_filter
    * socket_logger
    * msfd

msf > help repeat
Usage: repeat [OPTIONS] COMMAND...
Repeat (loop) a ;-separated list of msfconsole commands indefinitely, or for a
number of iterations or a certain amount of time.

    -t, --time SECONDS               Number of seconds to repeat COMMAND...
    -n, --number TIMES               Number of times to repeat COMMAND..
    -h, --help                       Help banner.
        --generate-completions str   Return possible tab completions for given string.
msf > help route
Route traffic destined to a given subnet through a supplied session.

Usage:
  route [add/remove] subnet netmask [comm/sid]
  route [add/remove] cidr [comm/sid]
  route [get] <host or network>
  route [flush]
  route [print]

Subcommands:
  add - make a new route
  remove - delete a route; 'del' is an alias
  flush - remove all routes
  get - display the route for a given target
  print - show all active routes

Examples:
  Add a route for all hosts from 192.168.0.0 to 192.168.0.255 through session 1
    route add 192.168.0.0 255.255.255.0 1
    route add 192.168.0.0/24 1

  Delete the above route
    route remove 192.168.0.0/24 1
    route del 192.168.0.0 255.255.255.0 1

  Display the route that would be used for the given host or network
    route get 192.168.0.11

msf > help save
Usage: save

Save the active datastore contents to disk for automatic use across restarts of the console

The configuration is stored in /Users/jpinkham/.msf4/config

msf > help sessions
Usage: sessions [options] or sessions [id]

Active session manipulation and interaction.

OPTIONS:

    -C <opt>  Run a Meterpreter Command on the session given with -i, or all
    -K        Terminate all sessions
    -S <opt>  Row search filter.
    -c <opt>  Run a command on the session given with -i, or all
    -d        List all inactive sessions
    -h        Help banner
    -i <opt>  Interact with the supplied session ID
    -k <opt>  Terminate sessions by session ID and/or range
    -l        List all active sessions
    -n <opt>  Name or rename a session by ID
    -q        Quiet mode
    -s <opt>  Run a script or module on the session given with -i, or all
    -t <opt>  Set a response timeout (default: 15)
    -u <opt>  Upgrade a shell to a meterpreter session on many platforms
    -v        List all active sessions in verbose mode
    -x        Show extended information in the session table

Many options allow specifying session ranges using commas and dashes.
For example:  sessions -s checkvm -i 1,3-5  or  sessions -k 1-2,5,6

msf > help spool
Usage: spool <off>|<filename>

Example:
  spool /tmp/console.log

msf > help threads
Usage: threads [options]

Background thread management.

OPTIONS:

    -K        Terminate all non-critical threads.
    -h        Help banner.
    -i <opt>  Lists detailed information about a thread.
    -k <opt>  Terminate the specified thread ID.
    -l        List all background threads.
    -v        Print more detailed info.  Use with -i and -l

msf > help unload
Usage: unload <plugin name>

Unloads a plugin by its symbolic name.  Use 'show plugins' to see a list of
currently loaded plugins.

msf > help advanced
Usage: advanced [mod1 mod2 ...]

Queries the supplied module or modules for advanced options. If no module is given,
show advanced options for the currently active module.


