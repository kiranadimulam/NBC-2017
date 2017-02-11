```
[root@kiran ~]# iscsiadm -m discovery -t st -p 10.10.10.239
10.10.10.239:3260,1 iqn.2009-05.com.tyronesystems:EMUYCP
[root@kiran ~]# iscsiadm -m node -l -p 10.10.10.239
Logging in to [iface: default, target: iqn.2009-05.com.tyronesystems:EMUYCP, portal: 10.10.10.239,3260] (multiple)
Login to [iface: default, target: iqn.2009-05.com.tyronesystems:EMUYCP, portal: 10.10.10.239,3260] successful.
[root@kiran ~]# fdisk -l

WARNING: GPT (GUID Partition Table) detected on '/dev/sda'! The util fdisk doesn't support GPT. Use GNU Parted.


Disk /dev/sda: 500.1 GB, 500107862016 bytes
255 heads, 63 sectors/track, 60801 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disk identifier: 0x00000000

   Device Boot      Start         End      Blocks   Id  System
/dev/sda1               1       60802   488386583+  ee  GPT
Partition 1 does not start on physical sector boundary.

Disk /dev/mapper/vg_kiran-lv_root: 53.7 GB, 53687091200 bytes
255 heads, 63 sectors/track, 6527 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disk identifier: 0x00000000


Disk /dev/mapper/vg_kiran-lv_swap: 4076 MB, 4076863488 bytes
255 heads, 63 sectors/track, 495 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disk identifier: 0x00000000


Disk /dev/mapper/vg_kiran-lv_home: 441.6 GB, 441605685248 bytes
255 heads, 63 sectors/track, 53688 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disk identifier: 0x00000000


Disk /dev/sdb: 16.1 GB, 16106127360 bytes
64 heads, 32 sectors/track, 15360 cylinders
Units = cylinders of 2048 * 512 = 1048576 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 524288 bytes
Disk identifier: 0x00000000

```
