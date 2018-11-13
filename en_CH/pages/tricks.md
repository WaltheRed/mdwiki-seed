# Linux tricks

## I/O redirection

    echo "foo" > bar  # write to file
    echo "foo" >> bar  # append to file

| "Symbol" | Description      |
| -------- | ---------------- |
| >        | stdout           |
| 1>       | "                |
| 2>       | stderr           |
| &>       | stdout & stdout  |
| 2>&1     | stderr to stdout |

[Source & more](https://www.tldp.org/LDP/abs/html/io-redirection.html)

## Files

Create a file (update the access and modification times)

    touch ./file

See: [touch](https://ss64.com/bash/touch.html)

## Disk speed

*if = input file*
*of = output file*

write 1GB w/ cache

    dd if=/dev/zero of=/root/testfile bs=1G count=1 oflag=direct

Write 1GB w/o cache

    dd if=/dev/zero of=/root/testfile bs=1G count=1 oflag=direct

Write 1k 512 bytes

    dd if=/dev/zero of=/root/testfile bs=512 count=1000 oflag=direct

## SAMBA share

[Source](http://archive.is/ZHuFF)

add lines to config file
    vi /etc/samba/smb.conf

    [public]
    path = /media/storage/
    public = yes
    writable = yes
    comment = smb share
    printable = no
    guest ok = yes

restart service
    systemctl restart smbd.service

## permissions (chown & chmod)

clone persmissions

    chown --reference=source target
    chmod --reference=source target

ss64:
[chown](https://ss64.com/bash/chown.html)
[chmod](https://ss64.com/bash/chmod.html)

## APT

    apt install ./name.deb

[Source](http://archive.is/R3s7R)

## convert between dos and unix files (using vim)

from dos to unix

    :set ff=unix

from unix to dos

    :set ff=dos

## Markdown

[add footnotes to GitHub-flavoured Markdown](https://stackoverflow.com/a/32119820)

# Windows

## autologon

### using the registry

```registry
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon]

"DefaultUserName"=""
"AutoAdminLogon"="0"
"DefaultPassword"=""
```


[How to turn on automatic logon in Windows](https://support.microsoft.com/en-us/help/324737/how-to-turn-on-automatic-logon-in-windows)

### using the gui tool

check & uncheck checkbox to get a prompt on OK

    netplwiz

```AutoAdminLogon``` must be 1 to use netplwiz