# linux

## Determine kernel version

```shell
uname -a
```

## Determine the linux distro and version

```shell
cat /etc/issue
cat /etc/os-release
cat /etc/lsb-release
cat /proc/version

lsb_release -a
hostnamectl
```

Source: [https://www.cyberciti.biz/faq/find-linux-distribution-name-version-number/](https://www.cyberciti.biz/faq/find-linux-distribution-name-version-number/)

## Display BIOS metadata -- no reboot needed

```shell
sudo dmidecode --type bios
```

## Ubuntu \(any Debian?\) -- check for non-LTS OS upgrades

```shell
sudo vi /etc/update-manager/release-upgrades
```
Make sure the "Prompt" value is set to "normal" and not "lts"

## Determine files within/installed by a package

```shell
apt-file list <package>   #NOTE: This works on any pkg, not just installed ones
dpkg -L <package>
```

## Show the total size of the current directory \(and all its subdirs\)

```shell
Linux:
sudo du --total --summarize --human-readable
```
```shell
BSD / MacOS
sudo du -c -s -h
```

## Determine locations of superblock backups

```shell
sudo mke2fs -n /dev/sda1
```
Needed to resolve "bad magic number in super-block" error


Reference: [https://linuxroutes.com/resolve-bad-magic-number-in-super-block-in-error/](https://linuxroutes.com/resolve-bad-magic-number-in-super-block-in-error/)


## Mount a raid 1 \(mirror\) drive

```shell
sudo mdadm --assemble --run /dev/md0 /dev/<partition to be mounted>
sudo mount /dev/md0
```
I needed this when I lost one of my mirrored drives and wanted to make a backup of the one that still worked

Reference: [https://serverfault.com/questions/383362/mount-unknown-filesystem-type-linux-raid-member](https://serverfault.com/questions/383362/mount-unknown-filesystem-type-linux-raid-member)

## Show only local, hardware, mounted drives

```shell
mount | grep -e '^\/dev'
```
This will limit the output to lines that start with "/dev", to cut down on noise from tmpfs, sysfs, proc, snaps, etc

## Change a user's default shell

```shell
sudo chsh -s /path/to/shell username
```

Source: [https://superuser.com/questions/379725/how-do-i-change-a-users-default-shell-in-osx](https://superuser.com/questions/379725/how-do-i-change-a-users-default-shell-in-osx)
