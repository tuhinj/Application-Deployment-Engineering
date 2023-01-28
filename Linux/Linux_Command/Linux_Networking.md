Linux Networking:
=================
ifconfig:
---------
- ifconfig - configure a network interface. Ifconfig is used to configure the kernel-resident network interfaces.

> ifconfig (user for show IP address, netmask, broadcast)
+ `enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500 inet 192.168.1.184  netmask 255.255.255.0 broadcast 192.168.1.255`

> ip a (use for show mac)
+ `1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000 link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00 inet 127.0.0.1/8 scope host lo valid_lft forever preferred_lft forever inet6 ::1/128 scope host valid_lft forever preferred_lft forever`

> ifconfig -V
+ `net-tools 2.10-alpha`

> 
