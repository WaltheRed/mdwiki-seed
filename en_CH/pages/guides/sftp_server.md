Setup a SFTP server
===================

Package
-------

    apt-get install openssh-server

How To
------

Create a group for your sftp enabled users.

    addgroup sftp_users

Create an user.

    adduser test_user

Take shell away from ther user (only for SFTP only users).

    usermod -s /bin/false test_user

Add user to sftp group.

    usermod -G sftp_users test_user

Prevent test_user from leaving his home directory.

    chown root:root /home/test_user
    chmod 755 /home/test_user

Create dir that the user can put stuff into.

    mkdir /home/test/upload
    chown test:sftp_users /home/test/upload

Source
------

[Source](https://web.archive.org/web/20171127160057/https://goneuland.de/debian-8-jessie-sftp-server-einrichten/)