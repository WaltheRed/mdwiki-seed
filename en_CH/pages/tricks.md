Linux tricks
============

Disk speed
----------

of=TARGET-FILE

Write 1GB w/ cache
    dd if=/dev/zero of=/root/testfile bs=1G count=1 oflag=direct

Write 1GB wo/ cache
    dd if=/dev/zero of=/root/testfile bs=1G count=1 oflag=direct

Write 1k 512 bytes
    dd if=/dev/zero of=/root/testfile bs=512 count=1000 oflag=direct

SAMBA share
-----------

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

