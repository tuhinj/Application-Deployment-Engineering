ENVIROMENT VARIABLES(echo, export, set, unset, expr):
=====================================================

=> ECHO:
--------
-> echo - display a line of text
-> Echo the STRING(s) to standard output.
       -n     do not output the trailing newline
       -e     enable interpretation of backslash escapes
       -E     disable  interpretation  of  backslash escapes (de‐fault)
       --help -> display this help and exit
       --version -> output version information and exit
	\\     backslash
	\a     alert (BEL)
	\b     backspace
	\c     produce no further output
	\e     escape
	\f     form feed
	\n     new line
	\r     carriage return
	\t     horizontal tab
	\v     vertical tab
	\0NNN  byte with octal value NNN (1 to 3 digits)
	\xHH   byte with hexadecimal value HH (1 to 2 digits)

# echo Hello World
> Hello World

# echo -n Hello World
> Hello World

# echo -e 'hello \bworld'
> helloworld

# echo -e 'hello \nworld'
> hello 
> world

# echo -e 'hello \tworld \vHow are you?'
> hello 	world 
>              How are you?

# a=12
# echo $a
> 12

# b=10
# echo $((a+b))
> 22

# echo $a+$b=$((a+b))
> 12+10=22

=> SET:
-------
-> The SET command is a built-in function in bash and few other cells which you can use to define the values of system variables. Set is not required to set a variable, there are various ways to do it.

-> Options of set command:
	-b (notify of job termination immdiately)
	-e (exit immediately if a command exits with a non-zero status)
	-m (Job control will be enabled)
	-o (Option-name: Allexport same as -a, Braceexpand same as -B, Errexit same as -e, Errtrace same as -E, Functrace same as -T)

-> export:
----------
-> The EXPORT command is used to create Enviroment Variables.

# x=4
# echo $x
> 4
# bash
# echo $x
>
# x=7
# echo $x
> 7
# exit
> exit
# echo $x
> 4
# export x [set the enviroment variables]
# echo $x
> 4
# bash
# echo $x
>4

=> UNSET:
---------
-> The UNSET command is a built-in function in bash which you can use to remove a variable which is set.

# echo $x
> 4
# export x [set the enviroment variables]
# echo $x
> 4
# bash
# echo $x
>4
# unset x [unset the enviroment variables]
# echo $x
> 
# bash
# echo $x
>

=> EXPR:
-------
- evaluate expressions.
-> The command expr computes a giver expression and displays the output
       ARG1 | ARG2 -> ARG1 if it is neither null nor 0, otherwise ARG2

       ARG1 & ARG2 -> ARG1 if neither argument is null or 0, otherwise 0

       ARG1 < ARG2 -> ARG1 is less than ARG2

       ARG1 <= ARG2 -> ARG1 is less than or equal to ARG2

       ARG1 = ARG2 -> ARG1 is equal to ARG2

       ARG1 != ARG2 -> ARG1 is unequal to ARG2

       ARG1 >= ARG2 -> ARG1 is greater than or equal to ARG2

       ARG1 > ARG2 -> ARG1 is greater than ARG2

       ARG1 + ARG2 -> arithmetic sum of ARG1 and ARG2

       ARG1 - ARG2 -> arithmetic difference of ARG1 and ARG2

       ARG1 * ARG2 -> arithmetic product of ARG1 and ARG2

       ARG1 / ARG2 -> arithmetic quotient of ARG1 divided by ARG2

       ARG1 % ARG2 -> arithmetic remainder of ARG1 divided by ARG2

#  expr 1 + 3
> 4
#  expr 1 - 4
> -3
#  expr 9 * 3
> 27
#  expr 8 / 3
> 6
#  expr 2 = 3
> 0
#  expr 3 % 2
> 1
#  x=hello
#  echo $x
> hello
#  expr length $x
> 5

=> HEADER FILE - SHEBANG (#!):
------------------------------
-> #!-This represents which interpreter a script should be interpreted with.
-> #!/bin/bash-This is a header command which represents it is a bash/shell script.
-> #!/bin/bash is this is not provided it often considers #!/bin/sh which would be same in most cases. When you put #!/bin/bash in your script, even if you run the script in a different shell, the kernel will know which shell to interpret it with.

# touch s.txt
# ls
> s.txt
#  nano s.txt 
>  "#!/bin/bash
echo 'Hello World!'"
#  sh s.txt
> Hello World!
#  bash s.txt 
> Hello World!

