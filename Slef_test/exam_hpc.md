```
[kiran@kiran Desktop]$ ssh root@10.10.10.153
root@10.10.10.153's password: 
Last login: Fri Feb 10 23:34:37 2017 from c18n2.netwebdel.com
[root@fs2client01 ~]# getenforce
Disabled
[root@fs2client01 ~]# 

[kiran@kiran Desktop]$ ssh root@10.10.10.154
The authenticity of host '10.10.10.154 (10.10.10.154)' can't be established.
RSA key fingerprint is e0:02:06:2d:53:09:06:48:29:39:12:1f:09:c6:2b:90.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.10.10.154' (RSA) to the list of known hosts.
root@10.10.10.154's password: 
Last login: Mon Jan 23 05:26:05 2017
[root@fs2client01 ~]# gwtenforce
bash: gwtenforce: command not found...
[root@fs2client01 ~]# getenforce
Disabled
[root@fs2client01 ~]# 

[kiran@kiran Desktop]$ ssh root@10.10.10.155
The authenticity of host '10.10.10.155 (10.10.10.155)' can't be established.
RSA key fingerprint is e0:02:06:2d:53:09:06:48:29:39:12:1f:09:c6:2b:90.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.10.10.155' (RSA) to the list of known hosts.
root@10.10.10.155's password: 
Last login: Mon Jan 23 05:26:05 2017
[root@fs2client01 ~]# getenforce
Disabled
[root@fs2client01 ~]# 
----------------------------------------------------------------------------------------------------------------------------------------------------------------

[root@fs2client01 ~]# systemctl status firewalld
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; disabled; vendor preset: enabled)

[root@fs2client01 ~]# systemctl status firewalld
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; disabled; vendor preset: enabled)
   Active: inactive (dead)
[root@fs2client01 ~]# systemctl status firewalld
● firewalld.service - firewalld - dynamic firewall daemon
   Loaded: loaded (/usr/lib/systemd/system/firewalld.service; disabled; vendor preset: enabled)
   Active: inactive (dead)
----------------------------------------------------------------------------------------------------------------------------------------------------------------
[root@fs2client01 ~]# hostname
c11mt
[root@fs2client01 ~]# hostname -i
10.10.10.153[root@fs2client01 ~]# vi /etc/hostname 
[root@fs2client01 ~]# hostname
c11n1t
[root@fs2client01 ~]# hostname -i
10.10.10.154

[root@fs2client01 ~]# hostname
c11n2t
[root@fs2client01 ~]# hostname -i
10.10.10.155
----------------------------------------------------------------------------------------------------------------------------------------------------------------
[root@c11mt yum.repos.d]# yum repolist all
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
repo id                                                                    repo name                                                                  status
centos                                                                     centos                                                                     enabled: 9,007
ganpbs                                                                     progang                                                                    enabled:    35
repolist: 9,042
[root@c11mt yum.repos.d]# 

[root@c11n1t yum.repos.d]# yum repolist all
Loaded plugins: fastestmirror, langpacks
centos                                                                                                                                       | 3.6 kB  00:00:00     
ganpbs                                                                                                                                       | 2.9 kB  00:00:00     
(1/3): centos/group_gz                                                                                                                       | 155 kB  00:00:00     
(2/3): ganpbs/primary_db                                                                                                                     |  26 kB  00:00:00     
(3/3): centos/primary_db                                                                                                                     | 5.3 MB  00:00:00     
Determining fastest mirrors
repo id                                                                    repo name                                                                  status
centos                                                                     centos                                                                     enabled: 9,007
ganpbs                                                                     progang                                                                    enabled:    35
repolist: 9,042

[root@c11n2t yum.repos.d]# yum repolist all
Loaded plugins: fastestmirror, langpacks
centos                                                   | 3.6 kB     00:00     
ganpbs                                                   | 2.9 kB     00:00     
(1/3): centos/group_gz                                     | 155 kB   00:00     
(2/3): ganpbs/primary_db                                   |  26 kB   00:00     
(3/3): centos/primary_db                                   | 5.3 MB   00:00     
Determining fastest mirrors
repo id                          repo name                        status
centos                           centos                           enabled: 9,007
ganpbs                           progang                          enabled:    35
repolist: 9,042
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
[root@c11mt yum.repos.d]# exportfs -ra
[root@c11mt yum.repos.d]# systemctl start nfs-server
[root@c11mt yum.repos.d]# systemctl enable nfs-server
Created symlink from /etc/systemd/system/multi-user.target.wants/nfs-server.service to /usr/lib/systemd/system/nfs-server.service.
[root@c11mt yum.repos.d]# systemctl status nfs-server
● nfs-server.service - NFS server and services
   Loaded: loaded (/usr/lib/systemd/system/nfs-server.service; enabled; vendor preset: disabled)
   Active: active (exited) since Sat 2017-02-11 00:25:50 IST; 27s ago
 Main PID: 3394 (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/nfs-server.service

Feb 11 00:25:50 c11mt systemd[1]: Starting NFS server and services...
Feb 11 00:25:50 c11mt systemd[1]: Started NFS server and services.
[root@c11mt yum.repos.d]# 

[root@c11n1t yum.repos.d]# yum install nfs-utils
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
Package 1:nfs-utils-1.3.0-0.21.el7.x86_64 already installed and latest version
Nothing to do
[root@c11n1t yum.repos.d]# systemctl start nfs-server
[root@c11n1t yum.repos.d]# systemctl enable nfs-server
Created symlink from /etc/systemd/system/multi-user.target.wants/nfs-server.service to /usr/lib/systemd/system/nfs-server.service.
[root@c11n1t yum.repos.d]# systemctl status nfs-server
● nfs-server.service - NFS server and services
   Loaded: loaded (/usr/lib/systemd/system/nfs-server.service; enabled; vendor preset: disabled)
   Active: active (exited) since Sat 2017-02-11 00:26:43 IST; 45s ago
 Main PID: 3369 (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/nfs-server.service

Feb 11 00:26:43 c11n1t systemd[1]: Starting NFS server and services...
Feb 11 00:26:43 c11n1t systemd[1]: Started NFS server and services.

[root@c11n2t yum.repos.d]# yum install nfs-utils
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
Package 1:nfs-utils-1.3.0-0.21.el7.x86_64 already installed and latest version
Nothing to do
[root@c11n2t yum.repos.d]# systemctl start nfs-server
[root@c11n2t yum.repos.d]# systemctl enable nfs-server
Created symlink from /etc/systemd/system/multi-user.target.wants/nfs-server.service to /usr/lib/systemd/system/nfs-server.service.
[root@c11n2t yum.repos.d]# systemctl status nfs-server
● nfs-server.service - NFS server and services
   Loaded: loaded (/usr/lib/systemd/system/nfs-server.service; enabled; vendor preset: disabled)
   Active: active (exited) since Sat 2017-02-11 00:27:55 IST; 13s ago
 Main PID: 3407 (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/nfs-server.service

Feb 11 00:27:54 c11n2t systemd[1]: Starting NFS server and services...
Feb 11 00:27:55 c11n2t systemd[1]: Started NFS server and services.
[root@c11n2t yum.repos.d]# 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
[root@c11n1t home]# cd /apps/
[root@c11n1t apps]# df -h
Filesystem          Size  Used Avail Use% Mounted on
/dev/sda2            99G  3.8G   90G   5% /
devtmpfs            2.0G     0  2.0G   0% /dev
tmpfs               2.0G     0  2.0G   0% /dev/shm
tmpfs               2.0G  8.7M  2.0G   1% /run
tmpfs               2.0G     0  2.0G   0% /sys/fs/cgroup
/dev/sda1           976M  115M  794M  13% /boot
tmpfs               396M     0  396M   0% /run/user/0
10.10.10.153:/apps   99G  3.7G   90G   4% /nfsroot/apps


[root@c11n2t apps]# df -h
Filesystem          Size  Used Avail Use% Mounted on
/dev/sda2            99G  3.7G   90G   4% /
devtmpfs            2.0G     0  2.0G   0% /dev
tmpfs               2.0G     0  2.0G   0% /dev/shm
tmpfs               2.0G  8.7M  2.0G   1% /run
tmpfs               2.0G     0  2.0G   0% /sys/fs/cgroup
/dev/sda1           976M  115M  794M  13% /boot
tmpfs               396M     0  396M   0% /run/user/0
10.10.10.153:/apps   99G  3.7G   90G   4% /nfsroot/apps
[root@c11n2t apps]# 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
[c11mt@c11n1t ~]$ df -h
Filesystem                Size  Used Avail Use% Mounted on
/dev/sda2                  99G  3.8G   90G   5% /
devtmpfs                  2.0G     0  2.0G   0% /dev
tmpfs                     2.0G     0  2.0G   0% /dev/shm
tmpfs                     2.0G  8.7M  2.0G   1% /run
tmpfs                     2.0G     0  2.0G   0% /sys/fs/cgroup
/dev/sda1                 976M  115M  794M  13% /boot
tmpfs                     396M     0  396M   0% /run/user/0
10.10.10.153:/apps         99G  3.7G   90G   4% /nfsroot/apps
10.10.10.153:/home/c11mt   99G  3.7G   90G   4% /home/c11mt

[c11mt@c11n2t ~]$ df -h
Filesystem                Size  Used Avail Use% Mounted on
/dev/sda2                  99G  3.7G   90G   4% /
devtmpfs                  2.0G     0  2.0G   0% /dev
tmpfs                     2.0G     0  2.0G   0% /dev/shm
tmpfs                     2.0G  8.7M  2.0G   1% /run
tmpfs                     2.0G     0  2.0G   0% /sys/fs/cgroup
/dev/sda1                 976M  115M  794M  13% /boot
tmpfs                     396M     0  396M   0% /run/user/0
10.10.10.153:/apps         99G  3.7G   90G   4% /nfsroot/apps
10.10.10.153:/home/c11mt   99G  3.7G   90G   4% /home/c11mt
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
```




















