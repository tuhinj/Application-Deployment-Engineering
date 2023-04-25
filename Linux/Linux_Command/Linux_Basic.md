#Working with Directories:
=========================
**-> man - an interface to the system reference manuals**

- man ls/pwd/mkdir

**-> pwd - print name of current/working directory**

- pwd

**-> ls - list directory contents**

- ls

- ls -l (long list with permission)

- ls -a (all file/dir)

- ls -la (all file/dir with permission list)

- ls -lah (all file/dir with permission list with size)	

**-> cd - cd use for enter any directory**

- cd - cd /home/user

- cd - cd / (root folder)

**-> mkdir - make directories**

- mkdir folder

**-> rmdir - remove empty directories**

- rmdir folder

- rmdir folder/folder2

Working With File:
==================
-> file — determine file type

# file text.txt

-> touch - change file timestamps

# touch file.txt

-> rm - remove files or directories

# rm file.txt

# rm -i file1.txt file2.txt

# rm -rf Folder/

# rm *.txt

# rm -r Folder/

-> cp - copy files and directories

# cp file.txt

# cp Folder/ Foldercopy/

-> mv - move (rename) files

# mv file1.txt file2.txt

# mv file1.txt /home/user/Documents

# cp Folder/ Foldercopy/

-> head - output the first part of files

# head text.txt

# head -5 text.txt

-> tail - output the last part of files

# tail text.txt

# tail -5 text.txt

-> cat - concatenate files and print on the standard output

# cat file.txt

# cat > file.txt

-> echo - display a line of text

# echo hello world!

# echo this is the file one > f1.txt 

-> more - file perusal filter for crt viewing

# more file.txt

-> grep,  egrep,  fgrep,  rgrep  -  print  lines  that  match

patterns

#grep p pip.txt

System Informaon:
=================
-> uptime - Tell how long the system has been running.

# uptime

-> free - Display amount of free and used memory in the system

# free

-> ps - report a snapshot of the current processes.

# ps -A

# ps aux

# ps -f

# ps -u user

-> kill - send a signal to a process

# kill -l

# kill -9 <code>

-> nice  -  run  a program with modified scheduling priority
	
# nice -19 <code>

-> df - report file system disk space usage

# df

# df -h

-> fdisk - manipulate disk partition table

# fdisk -l

-> lsblk - list block devices

# lsblk

-> top - display Linux processes

# top


Text Editores:
==============
-> nano - Nano's ANOther editor, inspired by Pico
	
	# nano file.txt
	
-> vim - Vi IMproved, a programmer's text editor
	
	# vi/vim file.txt (type - i, save+exit = wq, quite = q!)

Networking:
===========
-> ifconfig - configure a network interface
	
	# ifconfig
	
-> apt - command-line interface
	
	# apt update && apt uprade



