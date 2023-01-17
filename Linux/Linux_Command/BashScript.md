BASH/SHELL SCRIPT:
===================
-> A list of commands in a computer program called a shell script are executed by the command line interpreter known as the Unix/LINUX shell.

=> The SheBang (#!):
----------------
-> It's used to instruct the kernel on which interpreter to utilize when executing the commands in the file.
-> '#!' = It's called a shebang because the # symbol is called a hash, and the ! symbol is called a bang.
- it use in shell script text file.

Example:
--------
> $ nano hello.sh
- open text exitor and paste the below lines
* #!/bin/bash
* #This is my first script
* echo "Hello World!"
* echo "This is my first script...!"

> $ chmod 755 hello.sh

> $ ls -l
+ -rwxr-xr-x. 1 root root 94 Jan 17 13:58 hello.sh

>  ./hello.sh

 or

> $ sh hello.sh

 or 

> $ bash hello.sh
+ Hello World!
+ This is my first script...!

=> Secound Script:
------------------
> $ nano script1.sh

> $ cat script1.sh 
- #!/bin/bash
- #secound script
- pwd
- ls -l

> $ chmod 755 script1.sh
+ -rwxr-xr-x. 1 root root 40 Jan 17 14:59 script1.sh

> $ ./script1.sh 
+ /home/whoami/Documents/test
+ total 8
+ -rwxr-xr-x. 1 root root 94 Jan 17 13:58 hello.sh
+ -rwxr-xr-x. 1 root root 40 Jan 17 14:59 script1.sh

=> Variable Assigning:
----------------------
> $ nano script2.sh

> $ cat script2.sh
+ #!/bin/bash
+ #variable assigning...
+ name="Tuhin Joy"
+ age=23
+ echo $name $age
+ echo "Hello" $name
+ echo "Hello I'm $name and my age is $age"

> $ chmod 755 script2.sh
+ -rwxr-xr-x. 1 root root 140 Jan 17 16:33 script2.sh

> $ sh script2.sh
+ Tuhin Joy 23
+ Hello Tuhin Joy
+ Hello I'm Tuhin Joy and my age is 23

Example:
--------
> $ nano script3.sh

> $ cat script3.sh
+ #!/bin/bash
+ list=`ls`
+ dt=`date`
+ echo "Today date and time: " $dt
+ echo -e "Show the list of file and directory: " $list

> $ chmod 755 script3.sh
+ -rwxr-xr-x. 1 root root 119 Jan 17 16:51 script3.sh

> $ bash script3.sh
+ Today date and time:  Tue 17 Jan 16:53:15 EST 2023
+ Show the list of file and directory:  hello.sh script1.sh script2.sh script3.sh








