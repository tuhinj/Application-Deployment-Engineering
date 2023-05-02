Linux Networking:
=================
***ifconfig:***
----------------
- ifconfig - configure a network interface. Ifconfig is used to configure the kernel-resident network interfaces.

> ifconfig (user for show IP address, netmask, broadcast)
+ `enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500 inet 192.168.1.184  netmask 255.255.255.0 broadcast 192.168.1.255`

> ip a (use for show mac)
+ `1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000 link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00 inet 127.0.0.1/8 scope host lo valid_lft forever preferred_lft forever inet6 ::1/128 scope host valid_lft forever preferred_lft forever`

> ifconfig -V
+ `net-tools 2.10-alpha`

***Host:***
-----------
- host - DNS lookup utility
 
>host facebook.com

+ `whatsapp.com has address 157.240.15.60 whatsapp.com has IPv6 address 2a03:2880:f20c:1c2:face:b00c:0:167 whatsapp.com mail is handled by 10 mxa-00082601.gslb.pphosted.com.`

***NSLOOKUP:***
---------------
- nslookup - query Internet name servers interactively

> nslookup www.facebook.com

- `Server:127.0.0.5 Address: 127.0.0.53#53 Non-authoritative answer: Name:facebook.com Address: 157.240.235.35 Name:	facebook.com Address: 2a03:2880:f10c:381:face:b00c:0:25de`

***traceroute:***
------------------
- traceroute — trace the route to a host

> traceroute facebook.com

+ `traceroute to facebook.com (157.240.15.35), 64 hops max  1)   192.168.43.159  1.220ms  0.622ms  0.613ms 2)   *  *  *   3)   10.17.68.65  44.512ms  28.826ms  29.623ms `

***Netstat:***
--------------
-netstat  - Print network connections, routing tables, interface statis‐ masquerade connections, and multicast memberships

> netstat 

> netstat www.facebook.com

+ `netstat facebook.com Active Internet connections (w/o servers) Proto Recv-Q Send-Q Local Address           Foreign Address         State       tcp        0      0 Ubuntu-VivoBooK:55306   edge-z-p3-shv-04-:https ESTABLISHED`
