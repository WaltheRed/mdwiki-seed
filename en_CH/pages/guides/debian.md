setup debian
============

initalize sudo
--------------

[source](https://unix.stackexchange.com/a/425664)


enable su-mode

    su -

install sudo package

    apt-get install sudo -y

add user to sudoers group

    usermod -aG sudo username

Make sure your sudoers file have sudo group added. Run: `visudo` to modify sudoers file and add following line into it (if it is missing):

```bash
# Allow members of group sudo to execute any command
%sudo   ALL=(ALL:ALL) ALL
```

reboot!


install vbox guest additions
----------------------------

[install vbox guest additions](https://unix.stackexchange.com/a/286935)