LINUX ADVANCED DIRECTORY & FILE PERMISSION (ACL):
==============================================
Default file & dir permission:
---------------------------
	r = read (4)
	w = write (2)
	x = execute (1)
	- = no permission

Default file/Dir owner: root
Default file/Dir groupowner: root

Permission:
-----------
	# chown username filename/dirname 
	# chgrp groupname filename/dirname
	# chmod (u/g/o+rwx,u/g/o-rwx,777) filename/dirname
Permission:[r=4,w=2,x=1,rwx=7,rw=6,rx=5,wx=3] 

User & Group:
-------------
	User add: # useradd/adduser username
	Group add: # groupadd/addgroup groupname
	Add user in group: # gpasswd -M users groupname
	Remove user from group: # gpasswd -d users groupname 

	Show User: # cat /etc/passwd
	Show Group: # cat /etc/group
ACL: Access Control List:
============================
-> ACLs allow us to apply a more specific set of permissions to a file or directory without (necessarily) changing the base ownership and permissions.

	USER: user1, user2 
	User add in grp: # gpasswd -M user1,user2 testgrp1
	GROUP: testgrp1 => user1,user2 

Varify ACL permission:
----------------------
root@server:/home/tuhin/Test# getfacl test.txt
# file: test.txt
# owner: root
# group: root
user::rw-
group::r--
other::r--

ACL Permission Apply:
---------------------

User Permission:
root@server:/home/tuhin/Test# setfacl -m u:user1:rw-,u:user2:rwx test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
user:user1:rw-
user:user2:rwx
group::r--
mask::rwx
other::r--

Group Permission:
root@server:/home/tuhin/Test# setfacl -m g:testgrp1:rw- test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
user:user1:rw-
user:user2:rwx
group::r--
group:testgrp1:rw-
mask::rwx
other::r--

Other Permission:
root@server:/home/tuhin/Test# setfacl -m o::rw- test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
user:user1:rw-
user:user2:rwx
group::r--
group:testgrp1:rw-
mask::rwx
other::rw-

ACL Permission Remove:
----------------------

User Permission:
root@server:/home/tuhin/Test# setfacl -x u:user1:,u:user2: test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
group::r--
group:testgrp1:rw-
mask::rw-
other::rw-

Group Permission:
root@server:/home/tuhin/Test# setfacl -x g:testgrp1: test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
group::r--
mask::r--
other::rw-

Other Permission:
root@server:/home/tuhin/Test# setfacl -m o::--- test.txt 
root@server:/home/tuhin/Test# getfacl test.txt 
# file: test.txt
# owner: root
# group: root
user::rw-
group::r--
mask::r--
other::---

