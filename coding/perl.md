# Perl tips



## Install module in non-standard location
For whatever reason (maybe you don't have permission) you may want to install a Perl module outside the standard tree.

```shell
perl Makefile.PL PREFIX=/path/to/install
```


To build more modules, that depend on finding the modules you just installed (in a non-standard location), use this

```shell
PERL5LIB=/path/to/install perl Makefile.PL
```

## Ignore uninitialized variable warnings
Sometimes you don't care about all those uninitialized variables, but don't want to give up warnings altogether.

```perl
no warnings 'uninitialized';
```



## Determining if a module is in the path of @INC before using 'use' directive

wrap the 'use' in an 'eval' then wrap the 'eval' in a 'BEGIN' block

 ```perl
 BEGIN { unless (eval "use My::Mod") { warn "Couldn't load My::Mod: $@";}}
 ```


## CPAN installs
Are you always seeing "junoscript-perl" in the list of modules to be installed, even though you did not request it?  The solution is easy: stop using "install" when you run cpan from the command line.

```perl
      bad: 'cpan install My::Module'
     good: 'cpan My::Module'
```

# use the Perl::Critic module

Try using ```Perl::Critic``` against all your code to find problems based on recommendations from Perl Best Practices book.  This supplies a command line util ```perlcritic``` that you can run against your scripts or modules.

## easy way to determine module versions
add the following to $HOME/.bashrc:
```shell
function pmver () { perl -M$1 -le "print $1->VERSION"; }
```

Don't forget to "source $HOME/.bashrc" for the change to take effect


## Epoch time ==> human readable
```perl
#!/usr/bin/perl

my $epochtime = shift;
my $result = `date -d '1970-01-01 UTC +$epochtime seconds'`;
print $result;
```
