# Mutt tips

## sending JUST attachments, from the command line/scripts
```
echo | mutt -s $subject -a $file_to_attach user@somewhere.com
```
----

## sending HTML email (using file contents) from the command line/scripts
```
echo | mutt -e 'my_hdr Content-Type: text/html' -s $subject -i $html_file user@somewhere.com
```
----

## Deleting files based on date (from inside Mutt)

```
shift+T   (to tag)
~d dd/mm/yyyy-dd/mm/yyyy   (tag based on date)
;
d    (delete tagged messages)
```

###### Reference: [Mutt: select multiple messages](https://unix.stackexchange.com/questions/115310/mutt-select-multiple-messages)
----

## Mutt complains that mailbox is read-only when you try to delete messages
Change permissions on top level mail dir

```jpinkham@codegirl ~ $ sudo chmod 1777 /var/mail ```

Proof it worked, after I tried mutt again, and deleted messages:
```
jpinkham@codegirl ~ $ mutt
0 kept, 5 deleted.
```

###### Reference: [Getting a message from mutt that the mailbox is readonly if I use the `d' (delete) key](http://markmail.org/message/narknnybcdi4hcc2)
