Setup RAID 1
============

Packages
--------

    apt install mdadm parted

Prepare disks (repeat for both disks)
-----------------------------------

Create a new partition table.

    parted /dev/sde mklabel gpt

Create a new new partition.

    parted -a optimal -- /dev/sde mkpart primary 2048s -8192s

Enable RAID on device.

    parted /dev/sde set 1 raid on # asdf

Create RAID
-----------

Init the RAID.

    mdadm --create /dev/md0 --auto md --level=1 --raid-devices=2 /dev/sde1 /dev/sdf1

Make file system.

    mkfs.ext4 /dev/md0

Souce
-----

[ubuntuusers/Software-RAID](https://wiki.ubuntuusers.de/Software-RAID/)