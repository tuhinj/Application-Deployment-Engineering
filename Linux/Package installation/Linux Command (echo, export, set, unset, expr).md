ECHO:
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

$ echo Hello World
> Hello World

$ echo -n Hello World
> Hello World

$ echo -e 'hello \bworld'
> helloworld

$ echo -e 'hello \nworld'
> hello 
> world

$ echo -e 'hello \tworld \vHow are you?'
> hello 	world 
>              How are you?

$ a=12
$ echo $a
> 12

$ b=10
$ echo $((a+b))
> 22

$ echo $a+$b=$((a+b))
> 12+10=22

SET:
-> The SET command is a built-in function in bash and few other cells which you can use to define the values of system variables. Set is not required to set a variable, there are various ways to do it.

-> Options of set command:
	-b (notify of job termination immdiately)
	-e (exit immediately if a command exits with a non-zero status)
	-m (Job control will be enabled)
	-o (Option-name: Allexport same as -a, Braceexpand same as -B, Errexit same as -e, Errtrace same as -E, Functrace same as -T)

export:
-> The EXPORT command is used to create Enviroment Variables.

$ x=4
$ echo $x
> 4
$ bash
$ echo $x
>
$ x=7
$ echo $x
> 7
$ exit
> exit
$ echo $x
> 4
$ export x [set the enviroment variables]
$ echo $x
> 4

UNSET:
-> The UNSET command is a built-in function in bash which you can use to remove a variable which is set.
$ echo $x
> 4
$ export x [set the enviroment variables]
$ echo $x
> 4
$ bash
$ echo $x
>4
$ unset x [unset the enviroment variables]
$ echo $x
> 
$ bash
$ echo $x
>
