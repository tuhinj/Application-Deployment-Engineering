Bash/Shell Scripts:
===================
-> A list of commands in a computer program called a shell script are executed by the command line interpreter known as the Unix/LINUX shell.

The SheBang (#!):
----------------
-> It's used to instruct the kernel on which interpreter to utilize when executing the commands in the file.
-> '#!' = It's called a shebang because the # symbol is called a hash, and the ! symbol is called a bang.
- it use in shell script text file.

Ex:
---
> $ nano hello.sh
- open text exitor and paste the below lines
* #!/bin/bash
* #This is my first script
* echo "Hello World!"
* echo "This is my first script...!"
> $ chmod 755 hello.sh
+ -rwxr-xr-x. 1 root root 94 Jan 17 13:58 hello.sh
>  ./hello.sh
- or
> $ shell hello.sh
- or 
> $ bash hello.sh
+ Hello World!
+ This is my first script...!


