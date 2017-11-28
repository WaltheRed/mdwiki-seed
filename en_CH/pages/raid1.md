RAID 1
======

Install packages
    apt install mdadm parted

Partitioning (repeat for all disks)
-----------------------------------

For UEFI use GPT
    parted /dev/sde mklabel gpt

Create a single partition (with reserves)
    parted -a optimal -- /dev/sde mkpart primary 2048s -8192s

Init RAID 1
    parted /dev/sde set 1 raid on

Create RAID
-----------

RAID 1
    mdadm --create /dev/md0 --auto md --level=1 --raid-devices=2 /dev/sde1 /dev/sdf1

Make file system
    mkfs.ext4 /dev/md0