# Anisa-LPIC-1-Jan-2023-Fridays-HW7

## MohammadALi Heidari-LPIC1-Fridays-HW7

### Task 1: `/etc/fstab` Table structure:

The table itself is a 6 column structure, where each column designates a specific parameter and must be set up in the correct order. The columns of the table are as follows from left to right: 

- __Device:__ usually the given name or UUID of the mounted device (sda1/sda2/etc).
- __Mount Point:__ designates the directory where the device is/will be mounted. 
- __File System Type:__ nothing trick here, shows the type of filesystem in use. 
- __Options:__ lists any active mount options. If using multiple options they must be separated by commas. 
- __Backup Operation:__ this is a binary system where 1 = dump utility backup of a partition. 0 = no backup. This is an outdated backup method and should NOT be used. 
- __File System Check Order:__ Here we can see three possible outcomes.  0 means that fsck will not check the filesystem. Numbers higher than this represent the check order. The root filesystem should be set to 1 and other partitions set to 2. 

Now we will see some of the most important options:

- __auto and noauto:__ `auto` specifies that the device/partition should be automatically mounted on boot time and `noauto` specifies that the device should be explicitly mounted. When you execute `mount –a` all partition that has `auto` value set will get mounted automatically. The `root` partitions should have the `auto` option set so that the partition will get mounted automatically.

- __exec and noexec:__ The option `exec` specifies that the files residing in that device will be able to execute and `noexec` remove the execute feature. The partitions which are intended to keep non executable files like `/var` or `/tmp` can have `noexec` feature enabled for better security.

- __user and nouser:__ The `user` option specifies that the users will be able to mount the partitions and `nouser` specifies that only `root` user can mount any partitions. The `user` option should be set for devices like **floppy or CD-ROM** so that the users will be able to mount the device rather than being root.

- __ro and rw:__ The option `ro` specifies that the filesystem should be mounted as read-only and the option `rw` enables read-write.

- __sync and async:__ This specifies how the input and output to the filesystem should be done. `sync` means it should be done synchronously. That is, when you copy a file to the floppy, the changes are physically written to the floppy at the same time you issue the copy command. For `async`, the changes will be written only at the time of unmounting the floppy.

- __suid / nosuid:__ The option `suid` permit the operation of suid, and sgid bits and the option `nosuid` block the operation of suid and sgid bits.

- __Defaults:__ The normal default for Ext3 file systems is equivalent to `rw,suid,dev,exec,auto,nouser,async` (no acl support).

### Task 2:

- __Adding 4 disks (5GB, 7GB, 9GB, 11GB):__

![NEW HD](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/New%20HD.png?raw=true)
![5GB](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Add%205GB.png?raw=true)
![7GB](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Add%207GB.png?raw=true)
![9GB](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Add%209GB.png?raw=true)
![11GB](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Add%2011GB.png?raw=true)

__Confirmation__ :
![New HDs Created.png](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/New%20HDs%20Created.png?raw=true)

- __Make Partitions :__
![sdb1](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdb1.png?raw=true)
![sdb2](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdb2.png?raw=true)
![sdc1](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdc1.png?raw=true)
![sdc2](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdc2.png?raw=true)
![sdd1](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdd1.png?raw=true)
![sdd2](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdd2.png?raw=true)
![sdd3](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sdd3.png?raw=true)
![sde1](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sde1.png?raw=true)
![sde2](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/sde2.png?raw=true)

- __Physical vol :__
![Physical vol1](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/physical%20vol1.png?raw=true)
![Physical vol2](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/physical%20vol2.png?raw=true)

- __vol group :__
![vol group](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/vol%20group%20created.png?raw=true)

- __logical vols :__
![logical vols](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/logical%20vols%20created.png?raw=true)

- __formatting  :__
![formatting](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Formating.png?raw=true)

- __mounting   :__
![temp](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/temporary%20mount.png?raw=true)
![perm](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/permenant%20mount.png?raw=true)

- __vol group extended   :__
![vol group extended](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/Vol%20group%20extended.png?raw=true)

- __logical vols resize   :__
![logical vols resize](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/logical%20vols%20resize.png?raw=true)

- __resize confirmation   :__
![resize confirmation](https://github.com/mdhb9717/Anisa-LPIC-1-Jan-2023-Fridays-HW7/blob/main/resize%20confim.png?raw=true)
