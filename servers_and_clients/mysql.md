# MySQL / MariaDB
---

# Formatting output

## Truncate long fields for easier display
use ```SUBSTRING(fieldname,position,length)```

gotcha: first character is position "1" NOT "0", as you would expect

example, to view just the first 15 characters of 'myfield':
```
mysql> SELECT SUBSTRING(myfield,0,15) FROM tablename
```
To display from character 10 forward:
```
mysql> SELECT SUBSTRING(myfield,10) FROM tablename
```

## Show epochtime in human readable format
```
mysql> SELECT from_unixtime(fieldname) FROM tablename
```

## Format output in 1 field per line
just add ```<space> \G``` to the end of your query
```
mysql>  $query  \G;
```


## Use a pager with multi-screen results
You can run your results through an external pager program, rather than trying to scroll back within your terminal window.
```
mysql> pager less -niSFX
```
To turn it off
```
mysql> nopager
```


# Common actions

## See warnings when an update/delete/insert reports warnings
```
mysql> show warnings;
```

NOTE: You must run this IMMEDIATELY after a command that reports "warnings > 1", or you won't be able to see them

## Run commands in a flatfile (ex: output of mysqldump)
```shell
mysql $db_name < $filename
```

## Run single command and output results (without formatting)
```shell
echo "$command_string" | mysql -u $username -p -h $mysql_server -D $db_name
```

## See what processes and queries are running
```
show processlist;
```

## Creating a user

You must be logged in, as root, to the mysql db and use
"-D mysql" from the cmd line (or "use mysql" from within the cli)
### Examples:
```
mysql> GRANT ALL PRIVILEGES ON *.* TO monty@localhost
    ->     IDENTIFIED BY 'some_pass' WITH GRANT OPTION;
mysql> GRANT ALL PRIVILEGES ON *.* TO monty@'%'
    ->     IDENTIFIED BY 'some_pass' WITH GRANT OPTION;
mysql> GRANT RELOAD,PROCESS ON *.* TO admin@localhost;
mysql> GRANT USAGE ON *.* TO dummy@localhost;
```

format:
```
      GRANT ["ALL PRIVILEGES"|list privs] ON <dbname>.<tablename> to user@host
      IDENTIFIED BY 'some_pass' WITH GRANT OPTION;
```

## Empty out a table
```
mysql> TRUNCATE $table;
```

## Foreign Keys
NOTE: This is for MySQL v4.x

### Requirements
1) table type must be InnoDB  (requires flag set when mysql is compiled)

2) all fields that are to be foreign keys must be indexed

### Adding foreign keys
#### to update an existing table:
```
     ALTER TABLE mytable
     ADD CONSTRAINT field1_id_FK FOREIGN KEY (field1) REFERENCES mytable2(id);
```
#### OR if creating new table:
```
  CREATE TABLE config (
   provider_id int(11) NOT NULL default '0',
   dns_server varchar(100) NOT NULL default '',
   PRIMARY KEY  (provider_id,dns_server),
   KEY dns_server (dns_server),
   CONSTRAINT `0_999` FOREIGN KEY (`provider_id`) REFERENCES `providers` (`id`)
  ) TYPE=InnoDB;
```

## ORDER BY/GROUP BY/HAVING
### Example

```
select count(site) AS count,site
FROM webhistory
GROUP BY site
HAVING count(site) > 1 ORDER BY count;
```
output:
```
+-------+---------------------------+
| count | site                      |
+-------+---------------------------+
|     4 | feeds.gawker.com          |
|     3 | dev.mysql.com             |
|     2 | courts.state.va.us        |
|     2 | woot.com                  |
+-------+---------------------------+
```
