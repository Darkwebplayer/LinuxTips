# Breaking linux root password

## Normal Way

- restart the system

- if you dont see the grub menu hold `shift` key to bring it up

From here on there are two ways 

1. to to go to recovery mode and enterr root and reset the passwd, user passwords can be reset this way

2. edit grub and enter bash

### 2ndway

- press `e` on grub screen

- You need to modify it or change it from “_read-only_” mode to “_read-write_” mode. Find the line beginning with `“Linux.”` After, look for `“ro,”` and change it `“rw.”` Add `init=/bin/bash` at the end of the line.

-now you will be in root

- `mount -n -o remount,rw /`
- change password using `passwd` 
- `exec /sbin/init` 
- now your password will be resetted

## Using live cd

- open terminal in live os

-`sudo su` to become root

- fdisk -l to view file system and file the linux drive which password you dont know

- `mkdir  /mnt/recover` and `mount  /dev/sda1<you partition name>  /mnt/recover` 

- `chroot  /mnt/recover` we are pretending to be on the regular Linux filesystem. This is simply known as chrooting.

- now change the password using `passwd` and unmount the partion

- voila your password has been changed


## Redhat Linux

- go to the grub screen and press `e` as we did erlier and find the like begins with `Linux` this time add `rd.break` at the end of the line and then `console=tty1`.

- then press start `cntrl+x` most cases.

- now mount the system to /sysroot `mount -o remount.rw /sysroot

- now chroot /sysroot

- now cahnge the password using `passwd` and `touch /.autorelabel` to relabel the file system

- Finally exit
