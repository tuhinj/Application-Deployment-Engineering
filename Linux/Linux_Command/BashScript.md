BASH/SHELL SCRIPT:
===================
-> A list of commands in a computer program called a shell script are executed by the command line interpreter known as the Unix/LINUX shell.

=> The SheBang (#!):
----------------
-> It's used to instruct the kernel on which interpreter to utilize when executing the commands in the file.
-> `#!` = It's called a shebang because the 
- `#` symbol is called a hash
- `!` symbol is called a bang
* So `#!` it's called `shebang`
- `#!/bin/bash` it use in shell script text file.
- script can exicute by (bash 'scriptName', sh 'scriptName', ./'scripName')

Example 1:
---------
> $ nano hello.sh
- open text exitor and paste the below lines
* #!/bin/bash
* #This is my first script
* echo "Hello World!"
* echo "This is my first script...!"

> $ sudo chmod 755 hello.sh

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

> $ sudo chmod 755 script1.sh
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

> $ sudo chmod 755 script2.sh
+ -rwxr-xr-x. 1 root root 140 Jan 17 16:33 script2.sh

> $ sh script2.sh
+ Tuhin Joy 23
+ Hello Tuhin Joy
+ Hello I'm Tuhin Joy and my age is 23

Example 2:
----------
> $ nano script3.sh

> $ cat script3.sh
+ #!/bin/bash
+ list=`ls`
+ dt=`date`
+ echo "Today date and time: " $dt
+ echo -e "Show the list of file and directory: " $list

> $ sudo chmod 755 script3.sh
+ -rwxr-xr-x. 1 root root 119 Jan 17 16:51 script3.sh

> $ bash script3.sh
+ Today date and time:  Tue 17 Jan 16:53:15 EST 2023
+ Show the list of file and directory:  hello.sh script1.sh script2.sh script3.sh

Example 3:
----------
> $ nano script4.sh

> $ cat script4.sh 
+ #!/bin/bash
+ echo "Math oprations"
+ let a=12*2+6
+ let b=6/3*15
+ echo A=$a
+ echo B=$b

> $ sudo chmod 755 script4.sh 
+ -rwxr-xr-x. 1 root root  83 Jan 18 00:11 script4.sh

> bash script4.sh
+ Math oprations
+ A=30
+ B=30

Example 4:
----------
> $ nano script5.sh

> $ sudo chmod 755 script5.sh

> $ cat script5.sh
+ #!/bin/bash
+ x="$((5*6-4))"
+ y=$[5*6-4]
+ echo X=$x
+ echo Y=$y

> $ sh script5.sh
+ X=26
+ Y=26

Example 5:
----------
> $ nano ex1_script.sh

> $ cat ex1_script.sh
+ #!/bin/bash
+ p_yr=`date +'%Y'`
+ echo -n "Enter your name: "
+ read NAME
+ echo -n "Enter your age: "
+ read AGE
+ let fif_yr=(50-$AGE)+$p_yr
+ echo Hello $NAME. You will be 50 years old in $fif_yr

> $ sudo chmod 755 ex1_script.sh 

> $ sh x1_script.sh 
+ Enter your name: TuhinJOy
+ Enter your age: 23
+ Hello TuhinJOy. You will be 50 years old in 2050

Example 6:
----------
> $ nano ex2_script.sh

> $ sudo chmod 755 ex2_script.sh

> $ cat ex2_script.sh
+ #!/bin/bash
+ echo "Create a Directory"
+ mkdir /tmp/test00
+ echo "Create 3 file and list"
+ cd /tmp/test00/
+ touch  file01 file02 file03
+ ls -l
+ pwd

> $ sh ex2_script.sh
+ Create a Directory
+ Create 3 file and list
+ total 3
+ -rw-rw-r--. 1 whoami whoami 0 Jan 18 06:48 file01
+ -rw-rw-r--. 1 whoami whoami 0 Jan 18 06:48 file02
+ -rw-rw-r--. 1 whoami whoami 0 Jan 18 06:48 file03
+ /tmp/test00

=> Conditional Statment (if..else):
-----------------------------------
* `-eq ((==)) = Equle`
* `-ne ((!=))= not Equle`
* `-lt ((<))= less than`
* `-ge ((>))= greater than`
* `-a, && = and`
* `-o, || = or`


Example 7:
----------
> $ cat if_else.sh 
+ #!/bin/bash
+ a=10
+ if [ $a -eq 10 ]

or

+ if (( $a == 5 ))
+ then
+ 	echo "Hello There this is a true condition"
+ fi

> $ sudo chmod +x if_else.sh
+ -rwxr-xr-x  1 root root    88 Jan 24 01:08 fi_else.sh

> $ ./if_else.sh
+  Hello There this is a true condition 

Example 7:
----------
> $ cat if_else1.sh
+ #!/bin/bash
+ a=10
+ if (( $a == 5 ))
+ then
+        echo "Hello There this is a true condition"
+ elif [ $a -ge 5 ]
+ then
+        echo "This Condition is True...!!!The number is geter then 5"
+ elif (( $a < 5 ))
+ then
+        echo "This Condition is True...!!!The number is less then 5"
+ else
+        echo "Sorry The condition is False......!!!!!!"
+ fi

> $ sudo chmod +x if_else1.sh
+ -rwxr-xr-x  1 root root    88 Jan 24 01:08 fi_else.sh

> $ ./if_else1.sh
+  This Condition is True...!!!The number is less then 5

Example 8:
----------
> $ cat if_else2.sh 
+ #!/bin/bash
+ x=23
+ if [ $x -le 30 ] && [ $x -ge 20 ]

or

+ if [[ $x -le 30 && $x -ge 20 ]]

or

+ + if [ $x -le 30 -a $x -ge 20 ]
+ then
+	echo "It's Correct..!"
+ else
+	echo "It's Wrong...!"
+ fi

> $ sudo chmod +x if_else2.sh 
+ -rwxr-xr-x  1 root root   112 Jan 24 01:52 if_else2.sh

> # ./if_else2.sh
+ It's Correct..!

=> Loop in shell script:
------------------------
-> The types of loops:

* The while loop
* The for loop
* The until loop
* The select loop

While Loop:
-----------
* `-eq ((==)) = Equle`
* `-ne ((!=))= not Equle`
* `-lt ((<))= less than`
* `-ge ((>))= greater than`
* `-a, && = and`
* `-o, || = or`

> $ cat while_loop.sh 
+ #!/bin/bash
+ num=0
+ while [ $num -lt 5 ]

or

+ until [ $num -ge 5 ]
+ do
+	echo "$num"
+	num=$((num+1))
+ done

> $ sudo chmod 755 while_loop.sh
> $ ./while_loop.sh 
+ 0
+ 1
+ 2
+ 3
+ 4

For Loop:
---------
* `-eq ((==)) = Equle`
* `-ne ((!=))= not Equle`
* `-lt ((<))= less than`
* `-ge ((>))= greater than`
* `-a, && = and`
* `-o, || = or`

> $ cat for_loop.sh 
+ #!/bin/bash
+ for i in 1 2 3 4 5
+ do
+	echo $i
+ done

> $ sudo chmod 755 for_loop.sh

> $ ./for_loop.sh 
+ 1
+ 2
+ 3
+ 4
+ 5

Example 9:
----------
> $ cat for_loop1.sh
+ #!/bin/bash
+ for i in {0..100}
+ do
+	echo $i
+ done

> $ sudo chmod 755 for_loop1.sh

> $ ./for_loop1.sh 
+ 1
+ 2
+ .
+ .
+ 100

Example 10:
-----------
> $ cat for_loop2.sh 
+ #!/bin/bash
+ for i in {0..20..2} {start..ending..increment}
+ do
+	echo $i
+ done

> $ sudo chmod +x for_loop2.sh

> $ bash for_loop2.sh 
+ 0
+ 2
+ 4
+ 6
+ 8
+ 10
+ 12
+ 14
+ 16
+ 18
+ 20
+ {start..ending..increment}

Example 11:
-----------
> $ cat for_loop3.sh
+ #!/bin/bash
+ for (( i=0; i<10;  i++))
+ do
+	echo $i
+ done

> $ sudo +x for_loop3.sh

> ./for_loop.sh
+ 0
+ 1
+ 2
+ 3
+ 4
+ 5
+ 6
+ 7
+ 8
+ 9

Script Input:
-------------
> $ cat input2.sh 
 
+ #!/bin/bash

+ #echo $1 $2 $3 #Show the input three text...

+ args=("$@")

+ #echo ${args[0]} ${args[1]} ${args[2]} #Show the input three text...

+ echo $@ #Show the input line of text...

+ echo $# #Show the input length...

