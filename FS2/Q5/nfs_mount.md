```
[root@fs2client01 ~]# showmount -e
clnt_create: RPC: Port mapper failure - Unable to receive: errno 111 (Connection refused)
[root@fs2client01 ~]# showmount -e 10.10.10.239
clnt_create: RPC: Program not registered
[root@fs2client01 ~]# showmount -e 10.10.10.239
Export list for 10.10.10.239:
/storage/disk1/Artwork_Ingest 10.10.10.33
[root@fs2client01 ~]# mount -t nfs 10.10.10.239:/storage/disk1/Artwork_Ingest /mnt  
[root@fs2client01 ~]# df -h
Filesystem                                  Size  Used Avail Use% Mounted on
/dev/sda2                                    99G  3.7G   90G   4% /
devtmpfs                                    2.0G     0  2.0G   0% /dev
tmpfs                                       2.0G     0  2.0G   0% /dev/shm
tmpfs                                       2.0G  190M  1.8G  10% /run
tmpfs                                       2.0G     0  2.0G   0% /sys/fs/cgroup
/dev/sda1                                   976M  115M  794M  13% /boot
10.10.10.239:/storage/disk1/Artwork_Ingest   20G  543M   20G   3% /mnt
[root@fs2client01 ~]# 
```
