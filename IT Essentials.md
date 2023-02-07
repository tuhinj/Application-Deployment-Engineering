IT Essentials::
===============
#1. Operating systems:
---------------------
> An operating system is a type of system software that controls how software and hardware resources are used and offers basic services to other software applications.

* 32 bit OS - 86 (x86)
* 64 bit OS - x64 (x86_64)

#2. Kernel:
----------
> The kernel is a major part of an operating system that handles hardware and software activities.

#3. Linux vs Windows:
--------------------
Linux:
------
- Linux distribution is mostly free. Some are paid but at cheaper rates.
- Linux size is small compared to windows.
- Linux is extensible, or we can say customizable.
- It is available for all platforms.
- Malware Free
- More Secure
- Open Source
- Faster

* Linux 4 types:
----------------
1. Embedded (MINIX, Android, Tizen)
2. Desktop (Ubuntu, Mint, etc.)
3. Server (Red Hat, Debian, Oracal, CentOS, etc.)
4. Super Computer (Red Hat, SUSE, Ubuntu, etc.)

* Linux File System:
----------------------
> ext3
> ext4
> XFS

Windows:
--------
- It paid only and at higher rates than Linux distributions.
- Its size is quite large then Linux.
- It is not customizable.
- It supports only the defined platforms.

* Windows 3 types:
-----------------
1. Server(2012/2019 server)
2. Desktop(win10,win11)
3. Embedded(Windows Mobile)

* Windows File System:
----------------------
> NTFS (Any size file supported)

> FAT32 (Large size file not supported, encrypted not supported)

* Windows add user & Group:
---------------------------
> manual (add & delete user):
-----------------------------
> `this pc > manage > System Tools > Local Users and Groups > User > Right button > new user`

> `this pc > manage > System Tools > Local Users and Groups > User > select user click right button > delete `

> CMD (add & delete user):
--------------------------
> `Search CMD > open CMD with Administrator > command 'net user username password /add'`

> `Search CMD > open CMD with Administrator > command 'net user username /delete'`

> manual (add & delete Group):
-----------------------------
> `this pc > manage > System Tools > Local Users and Groups > Groups > select group click right button > new group > group name > add user in the group if you want`

> `this pc > manage > System Tools > Local Users and Groups > Groups > select group click right button > delete `


> CMD (add & delete Group):
--------------------------
> 

#Operationg System Run:
----------------------
+ Boot loader: "Complementary Metal Oxide Semiconductor(CMOS) it's program firmware, under the firmware two type of boot loader"

1. BIOS (Basic Input Output System)
------------------------------------
>> `BIOS > MBR (Master Boot Record) > Boot loader > OS Kernel > GUI/CLI`

2. UEFI (Unified Extensible Firmware Interface)
------------------------------------------------
>> `UEFI (EFI file system) > GPT (GUID Partition Table) / MBR (Master Boot Record) > Boot loader > OS Kernel > GUI/CLI`

MBR vs. GPT:
------------
+ MBR (Master Boot Record):
---------------------------
1. Primary Partitions (4)
2. Maximum Partition size 2TB (2^32 x 512 bytes/sector)

+ GPT (GUID Partition Table):
-----------------------------
1. Primary Partitions (128)
2. Maximum Partition size 9ZB (2^64 x 512 bytes/sector)

Windows OS Installation Planning:
---------------------------------
* MBR Partition:
---------------
> System Reserved - Reserved - 500MB

> C - NTFS/FAT32 - 30GB minimum

* GPT Partition:
----------------
> Recovery Partition - Recovery - 450MB

> EFI - FAT - 100MB

> Reserved Partition - NTFS - 350MB

> C - NTFS/FAT32 - 30GB minimum

Linux OS Installation Planning:
-------------------------------
* MBR Partition:
---------------
> /boot - XFS - 500MB

> / - XFS - 20GB minimum

> Swap - Swap - 2GB

> /backup - XFS - Required

* GPT Partition:
----------------
> /boot/efi - FAT - 450MB

> / - XFS - 20GB

> Swap - Swap - 2GB

> /backup - XFS - Required

#IP Addresses:
--------------
1. IPv4
2. IPv6

IPv4:
-----
> 32 Bits (0,1) or 4 Bytes

> 4 Parts

> Each Part called Octet

> Each Octet Seperated by Dot (.)

> Decimal Format (0-9)

> Example: 192.168.150.100 

> Each Octet 8bits (2^8)/256/(0-255). Ex:(0-255).(0-255).(0-255).(0-255)

> IPv4 Classes (5):
-------------------
- IP two part HOST and NETWORK

* Class A: (2^7)0-127 = Large Network [N.H.H.H] = 2^8 (N).2^24 (H) = (256N).(1,67,77,216H)

* Class B: (2^6)128-191 = Midium Network [N.N.H.H] = 2^16 (N).2^16 (H) = (65,536N).(65,536H)

* Class C: (2^5)192-223 = Small Network [N.N.N.H] = 2^24 (N).2^8 (H) = (1,67,77,216N).(256H)


+ Class D: (2^4)224-239 = Nulticast

+ Class E: (2^3)240-255 = Reserved

> IP Address Type:
------------------
1. Private IP

- Free

- Non Routable

- Use in Private Network

+ Range:
--------
> class A: [10.0.0.0 - 10.255.255.255]
> class B: [172.16.0.0 - 172.31.255.255]
> class C: [192.168.0.0 - 192.168.255.255]

2. Public IP

- Rental/ Lease Basis(500tk/IP)

- Use in Public Network

- Globally Unique & Routable

+ Range:
--------
> Without some reserved IP and private IP all IP are Public IP...!

IP Address Configuration:
-------------------------
> Static IP (Manual)

> `Control Panel\Network and Internet\Network and Sharing Center\Change adapter settings\select Ethernet\enter the ethernet properties\select 'Internet Protocol Version 4'`

> Dynamic IP (Auto)

> `Control Panel\Network and Internet\Network and Sharing Center\Change adapter settings\select Ethernet\enter the ethernet properties\select 'Internet Protocol Version 4'`

LoopBack:
---------
> Pinging the local host confirms that TCP/IP is installed and working on the local host.

+ IPv4: ping 127.0.0.1
 
+ IPv6: ping ::1

#Essential Commands:
--------------------
> ping - send ICMP ECHO_REQUEST to network hosts

* `ping google.com`

* `ping 8.8.8.8`

> nslookup - query Internet name servers interactively

* `nslookup google.com`

* `nslookup 8.8.8.8`

> traceroute/tracert — trace the route to a host

* `tracert googel.com` (windows)

* `tracert 8.8.8.8` (windows)

* `traceroute google.com`

* `traceroute 8.8.8.8`

> ip - show / manipulate routing, network devices, interfaces and tunnels

* `ip a`

* `ip all` (windows)

> dig - DNS lookup utility
 
* `dig google.com`

* `dig 8.8.8.8`

>  route - show / manipulate the IP routing table

* `route`

> netstat/nestat  - Print network connections, routing tables, interface statis‐tics, masquerade connections, and multicast memberships

* `netstat -n` (windows)

* `netstat -ntlp` (linux)

> ifconfig/ipconfig - configure a network interface

* `ipconfig /renew` (windows)

* `ifconfig`

* `ipconfig all` (windows)

* `ifconfig -s`

* `ifconfig -a`

#Port:
------
Two types of ports:
-------------------

> TCP (Transfer control protocal)

+ TCP is a connection-oriented protocol.

+ TCP is comparatively slower than UDP.

+ Lost data packets is only possible with TCP.

+ TCP uses handshake protocols.

> UDP (user datagram protocal)

+ UDP is a connectionless protocol.

+ UDP is faster, simpler, and efficient.

+ Lost data packets is not possible with UDP.

+ UDP uses no handshake protocols.

Most commonl used ports:
------------------------
- `20 & 21:  File Transfer Protocol (FTP).`

- `22: Secure Shell (SSH).`

- `25: Simple Mail Transfer Protocol (SMTP).`

