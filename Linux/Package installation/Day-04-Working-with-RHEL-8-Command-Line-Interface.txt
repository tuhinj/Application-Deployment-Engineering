########################################################
##################### Session :01 ######################
########################################################


Working with Linux CLI:
=======================
[student@desktop ~] $ 


~ = Home Directory  


Linux User's Types:
-------------------
লিনাক্স সিস্টেমে ৩ (তিন) ধরণের ইউজার একাউন্ট থাকে। 


 => root user: Administrator (#)                - সিস্টেমের অ্যাডমিন ইউজার। 
 => system user: service (mail/ftp/ssh/daemons) - cannot login (সিস্টেমে বিল্ট-ইন থাকে) 
 => regular user: student, guest, sakib ($)     - যে সকল ইউজার একাউন্ট 'root' কর্তৃক তৈরি করা হয়। 


[root@host1  desktop] # 
  1     2       3     4 
 
         1: user name    (যে ইউজার দিয়ে সিস্টেমে লগইন করা হয়েছে)
         2: hostname     (কম্পিউটারের/সিস্টেমের নাম)
        3: user's       (ইউজারের বর্তমান অবস্থান)
        4: user types (root: #, regular user: $)


Working with Linux Shells & Terminal:
------------------------------------
 User -> Keyboard -> Terminal/Application -> Shell -> Kernel -> Hardware (CPU/MEM/DISK)
           Screen <- Terminal/Application <- Shell <- Kernel <- Hardware


Linux Shell পরিচিতিঃ
------------------
 লিনাক্স অপারেটিং সিস্টেমের একটি গুরুত্বপূর্ণ ও স্পেশাল প্রোগ্রাম হচ্ছে লিনাক্স শেল। লিনাক্সের শেল ইউজারের কাছ থেকে কমান্ড
 গ্রহণ করে এবং যদি ইউজার কর্তৃক প্রদত্ত কমান্ড সঠিক হয়, তাহলে সিস্টেমের শেল এই কমান্ডকে কার্নেলের নিকট প্রেরণ করে 
অপারেটিং সিস্টেমের সঙ্গে তথ্য আদান-প্রদান করার জন্য লিনাক্স ইউজার ইন্টারফেস প্রদান করে। আবার প্রদত্ত কমান্ড যদি সঠিক
 না হয়, তাহলে  'Bash: Command not Found' দেখাবে। লিনাক্স শেল হচ্ছে একটি কমান্ড ল্যাঙ্গুয়েজ ইন্টারপ্রেটার,
যেটা কিবোর্ড অথবা ফাইল হতে কমান্ড গ্রহণ করে এবং যেকোনো Programming Syntax বা কমান্ডকে সরাসরি execute 
করতে পারে।   


 Types of Linux Shell:
 ---------------------
 => sh
 => Bash  (commonly used) 
 => cshell
 => tcshell
 => kshell 
 => zsh 


বর্তমানে কোন শেল ব্যবহার হচ্ছে এবং আমাদের সিস্টেমে এবং কি কি শেল ইন্সটল আছে সেটা জানার জন্য নিচের কমান্ডঃ 


[student@hostX Desktop] $ echo $SHELL
[student@hostX Desktop] $ chsh -l
 /bin/sh
 /bin/bash
 /usr/bin/sh
 /usr/bin/bash


Linux Consoles:
---------------
 => Pseudo Consoles (/dev/pts/x) or connection from GUI Terminal or Remote Terminal
 => Virtual Console (Telnet, SSH, RDP, VNC) 
 => Web Console using https (cockpit)
 => Physical Consoles: 
        => Ctrl + Alt + F1/F2: GUI 
        => Ctrl + Alt + F3-F6: CMD  (tty)


 Alt + Ctrl + F1 = GNOME Shell  (Activities)
 Alt + Ctrl + F2 = GNOME Classic Shell (Application/Start Menu)


Classic Desktop এর ক্ষেত্রেঃ 
------------------------
 Alt + Ctrl + F1 => GUI                       - :0
 Alt + Ctrl + F3 => new CMD terminal (F3-F6)  - tty3-tty6   


 নোটঃ ফিজিক্যাল কনসোল দিয়ে লগইন করলে এবং টার্মিনাল থেকে 'who' কমান্ড দিলে সেখানে 'tty' দেখা যাবে। উদাহরণ স্বরূপ কেউ যদি, Alt + Ctl + F3 দিয়ে লগইন করে, তাহলে 'who' কমান্ড দিলে 'tty3'।  কিছু কিছু ক্ষেত্রে গ্রাফিক্যাল টার্মিনালের ক্ষেত্রেও 'tty' বা ':0' দেখাবে।      


 => Press Ctl + Alt + F3
 
 Login: student
 pass: ****** 


 [student@hostX Desktop]$ su -      ; রেগুলার ইউজার থেকে 'root' ইউজারে সুইচ করা হল। 
  Password: ******


 [root@hostX ~]# exit            ; 'root' ইউজার থেকে বের হওয়া। 
 [student@hostX ~]$ exit         ; 'student' ইউজার থেকে লগ আউট হওয়া। 


Enable Web Console (Cockpit):
-----------------------------
# systemctl enable --now cockpit.socket 


 => Open Firefox web browser
 => type: https://localhost:9090


       username: root
       password: redhat 
 
Pass: 1Passw0rd@123


 লিনাক্সে বহুল ব্যবহৃত কিছু শর্টকাট কমান্ডঃ 
 -----------------------------
 $ ctrl + l = টার্মিনাল পরিষ্কার (clear) করার জন্য। 
 $ ctrl + shift + "t" গ্রাফিক্যাল ইউজার ইন্টারফেস দিয়ে (GUI) নতুন ট্যাব খোলার জন্য।   
 $ Ctrl + d   - কমান্ড কনসোলে লগ আউট করার জন্য ব্যবহার হয়। 
 $ Alt + F2   - নতুন কমান্ড রান করার জন্য।  (Type 'firefox' and press Enter) 


Linux Command Syntax/Pattern:
-----------------------------
প্রতিটি কমান্ড লাইন ইন্টারফেস ভিত্তিক (CLI) অপারেটিং সিস্টেম বা ডিভাইসে কমান্ড লাইন ইন্টারফেস নিয়ে কাজ করতে চাইলে, প্রত্যেকটি কমান্ডের ০৩ (তিন) টা পার্ট থাকে। প্রথম টা হচ্ছে কমান্ড, যেটা দিতেই হবে এবং শেষের টা হচ্ছে আর্গুমেন্ট। কিছু কিছু কমান্ড আর্গুমেন্ট ছাড়াই কাজ করে, আবার কিছু কিছু কমান্ড আর্গুমেন্ট ছাড়া কাজ করবেই না। আবার অনেক কমান্ডে আমরা কমান্ডের সাথে অপশন ব্যবহার করে থাকি। একটা কমান্ডের সাথে নানা রকম অপশন ব্যবহার করা যায় এবং একটি একটি অপশন ব্যবহার করে আলাদা আলাদা আউটপুট পাওয়া যায়। নিচের একটা কমান্ডের ০৩ (তিন) টা পার্ট দেখানো হয়েছেঃ 


    # command [options (-)] argument


 example:
 --------
    # date
    # cal
    # ping 
    # ping 127.0.0.1
    # ping -c4 127.0.0.1
    
 # ping --help 


উপরে দেখতে পাচ্ছি এখানে একটি কমান্ডে কমান্ড, অপশন এবং আর্গুমেন্ট সবই ব্যবহার করা হয়েছে। এখানে 'ping' হচ্ছে কমান্ড, '-c4' হচ্ছে অপশন এবং '127.0.0.1' হচ্ছে আর্গুমেন্ট। এই কমান্ডে শুধু 'ping' লিখে এন্টার চাপলে কাজ করবে না। কারণ, 'ping' কোন হোস্ট/নোড কে করবেন, এইজন্য অবশ্যই আর্গুমেন্ট ব্যবহার করতে হবে। 


একটা কমান্ডের সাথে অপশন ব্যবহার করে কিভাবে বিভিন্ন আউটপুট পাওয়া যায়, তার একটা উদাহরণ নিচে দেওয়া হয়েছে। এখানে 'ls' কমান্ডের সাথে '-l,-i,-a,-h' নানা অপশন ব্যবহার করে নানা ধরণের আউটপুট পাওয়া যাবে। পাশাপাশি আমরা চাইলে একসাথে সবগুলা অপশন ব্যবহার করতে পারি। 


[student@hostX Desktop]$ cd 
[student@hostX ~]$ ls        ; বর্তমান ডিরেক্টরির মধ্যে সকল ফাইল/ডিরেক্টরি দেখা যাবে। 
[student@hostX ~]$ ls -l     ; লম্বা লিস্ট (Properties) সহ দেখা যাবে। 
[student@hostX ~]$ ls -li    ; ফাইল/ডিরেক্টরির আইনোড (inode) সহ দেখা যাবে। 
[student@hostX ~]$ ls -la    ; লুকানো (Hidden) ফাইল সহ দেখা যাবে। 
[student@hostX ~]$ ls -lh    ; Human Readable (K/M/G) তে দেখা যাবে। 
[student@hostX ~]$ ls -laih  ; সকল অপশন একসাথে ব্যবহার করা হয়েছে। 


উপরে 'ls' কমান্ডের সাথে ব্যবহৃত অপশন সমূহের বিস্তারিত নিচে আলাপ করা হয়েছেঃ


 -l = list  (লম্বা লিস্ট বা বিস্তারিত দেখার জন্য এই অপশন টা ব্যবহার করা হয়) 
 -i = inode (প্রতিটি ফাইল/ডিরেক্টরির একটা ইন্ডেক্সিং নাম্বার থাকে যেটাকে বলা হয়ে আইনোড (inode), এটা মূলত সব ফাইলের আলাদা আলাদা।) 
 -a = all   (এই অপশন ব্যবহার করলে বর্তমান ডিরেক্টরির মধ্যের সকল লুকায়িত (Hidden) ফাইল/ডিরেক্টরিসহ দেখা  যাবে। )
 -h = human readble (ফাইলের সাইজ সাধারনত বাইট আকারে দেখায়। এই অপশন ব্যবহার করলে Kilo (K), Mega (M), Giga (G) আকারে দেখাবে।)
 
 ** আর যদি সবগুলা অপশন একসাথে ব্যবহার করা হয়, তাহলে সবগুলা অপশনের আউটপুট একসাথে দেখাবে।  


লিনাক্স ফাইল/ডিরেক্টরির কালার কোডঃ
-------------------------
লিনাক্স ভিত্তিক অপারেটিং সিস্টেমে অধিকাংশ কাজ কমান্ড লাইনেই করতে হবে। গ্রাফিক্যাল এনভায়রনমেন্টে কাজ করার সময় বিভিন্ন ফাইল/ডিরেক্টরির আইকন দেখে একটা ধারণা পাওয়া যায়, কোনটা কি ধরণের ফাইল বা ডিরেক্টরি। কিন্ত, কমান্ড লাইন ইন্টারফেস নিয়ে কাজ করার সময়ে আসলে সব কিছুই টেক্সট হিসেবে দেখা যায়। এইজন্য কোনটা কি ধরণের ফাইল বা ডিরেক্টরি এটা বাছাই করা একটু চ্যালেঞ্জ। কিন্ত, আমরা চাইলে কিছু কালার কোডের মাধ্যেমে লিনাক্সের বিভিন্ন ফাইল/ডিরেক্টরি চিনতে পারি, নিচে সেগুলার একটা লিস্ট দেওয়া হয়েছেঃ 


      Blue - Directory  
      B & W - File (text, pdf, ppt) 
      Red - Compress (rpm/zip/rar/tar)
      Green - Execute file (script)
      Yellow - Device (Terminal/CD/DVD/USB/SSD/HDD)
      Cyan - link file/audio
      Magenta - Picture/image/video


[student@hostX ~]$ pwd     ; present working directory


  "~"           => Home dir (root/regular user) 
  "/"           => root partition (/) (Computer)
  "/root" => 'root' ইউজারের হোম (~) ডিরেক্টরি। 
  "/home" => সকল রেগুলার ইউজারদের হোম (~) ডিরেক্টরি। 
    i.e.: /home/student


[student@hostX ~]$ => রেগুলার ইউজার 'student' এর home (~) ডিরেক্টরি। 


কিছু বেসিক কমান্ড যেগুলা লিনাক্সের সকল ডিস্ট্রিবিউশনের মধ্যে কাজ করবেঃ  
--------------------------------------------------
[student@hostX ~]$ w                           ; who are currently loggin (Details)
[student@hostX ~]$ who                         ; who are currently loggin (shorter)
[student@hostX ~]$ whoami 
[student@hostX ~]$ hostname
[student@hostX ~]$ tty
[student@hostX ~]$ date
[student@hostX ~]$ cal 
[student@hostX ~]$ cal 2021
[student@hostX ~]$ runlevel                       ;(5-GUI, 3-Minimal, n-none (এর আগে অন্য কোনো runlevel -এ প্রবেশ করে নাই) 
[student@hostX ~]$ uname -r                           ; kernel version
[student@hostX ~]$ uname                          ; OS name
[student@hostX ~]$ cat /etc/redhat-release        ; redhat/centos version
[student@hostX ~]$ top                                  ; task manager (বের হওয়ার জন্য 'q' প্রেস করতে হবে) 
[student@hostX ~]$ lastlog                          ; login details
[student@hostX ~]$ free -m                          ; RAM Info
[student@hostX ~]$ uptime                          : system UPtiem info
[student@hostX ~]$ ifconfig                          ; IP Address Info


[student@hostX ~]$ history                          ; list of privious command
[student@hostX ~]$ !25                                ; history থেকে '25' নাম্বার কমান্ডটি পুনরায় রান করার জন্য। 
[student@hostX ~]$ history -c                           ; history থেকে সকল কমান্ড মুছে দেওয়ার জন্য ব্যবহার করা হয়। 
[student@hostX ~]$ history


 Shutdown
 --------
[root@hostX ~]# init 0
[root@hostX ~]# poweroff
[root@hostX ~]# shutdown -h now      ; এখানে 'h' = halt বোঝায়। 
[root@hostX ~]# shutdown -h 5 now    ; এখন থেকে ৫ মিনিট পরে সিস্টেম বন্ধ (halt) হবে। 


restart:
--------
[root@hostX ~]# reboot
[root@hostX ~]# init 6
[root@hostX ~]# shutdown -r now                   ;  এখানে '-r' = reboot বোঝায়। 
[root@hostX ~]# shutdown -r 5 now    ; এখন থেকে ৫ মিনিট পরে সিস্টেম রিবুট (reboot) হবে। 


########################################################
##################### Session :02 ######################
########################################################
   
Linux Directory Structure:
-------------------------
[student@hostX ~]$ cd /
[student@hostX /]$ ls


backup  boot  etc   lib    media  opt   root  sbin  sys  usr
bin     dev   home  lib64  mnt    proc  run   srv   tmp  var


 /bin - Binary Files (যে সকল কমান্ড গুলা রেগুলার ইউজার কর্তৃক রান করা হয়), যেমনঃ ls, cd, pwd, who, cal, date etc. 
 
 /boot - সিস্টেম বুট (boot) সম্পর্কিত ফাইল। যেমনঃ boot loader, Kernel, filesystem এখানে থাকবে। 
 
 /dev - সিস্টেমের সকল ডিভাইস টাইপের ফাইল গুলা এখানে থাকে। যেমনঃ DVD, HDD, Printer, sound, Terminal, Serial/Prallel Devices. 


 /etc - সকল সিস্টেম এবং সার্ভার কনফিগারেশন ফাইল। ইউজার/গ্রুপ ডাটাবেজ, সিস্টেম ও সার্ভার কনফিগারেশন, প্রোফাইল, সিকিউরিটি  সম্পর্কিত ফাইল। 


 /home - সকল রেগুলার ইউজারদের হোম ডিরেক্টরি। যেমনঃ student, tamim, sumon (FTP, Email, File সার্ভার ইউজার)। 


 /lib -  সিস্টেমের সকল library ফাইল এবং কার্নেল মডিউল থাকে '/lib' এর ভিতরে। '/bin' & '/sbin' ডিরেক্টরিতে যত কমান্ড আছে, এই কমান্ড         এক্সিকিউট করতে library দরকার হয়। 


 /media - এটা ডিফল্ট ভাবে ফাঁকা থাকে। মিডিয়া টাইপের ডিভাইস (DVD/ISO) বা এক্সটারনাল ডিভাইস এই লোকেশনে মাউন্ট করে এক্সেস করা হয়। 


 /mnt - mount point (DVD/HDD/USB/Network Share) -
 
 /opt - optional (empty) - এই ডিরেক্টরি সাধারণত ফাঁকা  থাকে। বিভিন্ন ফাইল/আপ্লিকেশন/সার্ভিস টেস্ট করার জন্য এই ডিরেক্টরি ব্যবহার করা হয়। 


 /proc - Also called 'proFS' system process related info (CPU, RAM, Process, Running Apps, Driver, Modules and Kernel)


 /root - লিনাক্সের অ্যাডমিন ইউজার (root) এর হোম ডিরেক্টরি। সাধারণ ইউজাররা (student,tarek,sadia) এখানে প্রবেশ করতে পারে না। 


 /run - service running data. Runtime data for processes started since the last boot.  


 /sbin  - System Binary Files (যে সকল কমান্ড গুলা root ইউজার কর্তৃক রান করা হয়), যেমনঃ useradd, poweroff, fdisk, reboot এই কমান্ড                        সমূহ '/sbin' ডিরেক্টরিতে পাওয়া যাবে। 


 /srv - Sort for Service. User's (/home/*) service related data. Like WWW, FTP, Email etc.


 /sys - Sort for system. '/sys' directory as a virtual filesystem (sysfs) mounted under /sys. 
        similar as proc.
 
 /tmp - Temporary ফাইল সমূহ এখানে থাকে। সিস্টেম প্রতি ১০ দিন অন্তর অন্তর নিজে থেকেই মুছে (Delete) করে দিবে। 


 /usr - thirdparty software install location
 
 /var - varibale file (mail/log/hosting/ftpdata)


[student@hostX ~]$ cd  [enter]  ; আমরা যে ডিরেক্টরিতেই থাকি না কেন, 'cd' কমান্ড দিলে সরাসরি হোম ডিরেক্টোরিতে ফিরে আসা যাবে। 
[student@hostX ~]$ cd /         ; 'cd' কমান্ডের সাথে '/' ব্যবহার করে এন্টার প্রেস করলে রুট পার্টিশনে (/) প্রবেশ করা যাবে। 
[student@hostX /]$ ls       ; আমরা বর্তমানে রুট পার্টিশনের (/) মাঝে অবস্থান করছি, এখানকার সকল ফাইল/ডিরেক্টরি দেখার জন্য 'ls' কমান্ড দিতে হবে।  
[student@hostX /]$ cd


        =>  cd  /dir1/dir2/dir3      ; Linux Directory Path


        =>  C:\dir1\dir2\dir3>       ; Windows Directory Path


[student@hostX ~]$ cd /var/spool/mail
[student@hostX mail]$ pwd                 ; বর্তমানে কোন অবস্থানে আছি, সেটা দেখা যাবে। 
 /var/spool/mail
[student@hostX mail]$ ls
[student@hostX mail]$ cd  ..            ; এক ধাপ পিছনের (Parent) ডিরেক্টরিতে যাওয়ার কমান্ড। 
[student@hostX spool]$ cd  -            ; পূর্বের ডিরেক্টরিতে ফিরে যাওয়ার কমান্ড। 
[student@hostX mail]$ cd                ; সরাসরি '/home/$user' ডিরেক্টরিতে ফিরে যাওয়ার কমান্ড। 
[student@hostX ~]$ ls
[student@hostX ~]$ cd Music 
[student@hostX Music]$ cd ../Videos
[student@hostX Videos]$ ls
[student@hostX Videos]$ pwd       


[student@hostX Videos]$ cd 
[student@hostX ~]$ mkdir linux21
[student@hostX ~]$ ls
[student@hostX ~]$ cd linux21
[student@hostX linux21]$ ls
[student@hostX linux21]$ pwd
[student@hostX linux21]$ mkdir day4
[student@hostX linux21]$ cd day4
[student@hostX day4]$ ls
[student@hostX day4]$ pwd


Test: Graphically (home/...........)


 class work:
 -----------
[student@hostX day4]$ touch file1                ; ফাইল তৈরির জন্য 'touch' ব্যবহার করা হয়। 
[student@hostX day4]$ ls                         ; ফাইল দেখার জন্য 'ls' কমান্ড
  file1


[student@hostX day4]$ touch index.html           ; এক্সটেনশন সহ ফাইল তৈরির কমান্ড। 
[student@hostX day4]$ touch file2 file3 file4    ; একাধিক ফাইল একসঙ্গে তৈরি করার কমান্ড। 
[student@hostX day4]$ ls                                        ; ফাইল গুলা দেখার জন্য 'ls' কমান্ড
[student@hostX day4]$ mkdir dir1 dir2 dir3       ; এক কমান্ডের মাধ্যমে একাধিক ডিরেক্টরি তৈরি করার কমান্ড। 
[student@hostX day4]$ ls                           ;  আউপুট দেখার জন্য 'ls' কমান্ড
[student@hostX day4]$ touch doc{1..10}           ; দশটি (১০) ফাইল সিরিয়ালি তৈরি করার কমান্ড। 
[student@hostX day4]$ ls                           ;  আউপুট দেখার জন্য 'ls' কমান্ড
[student@hostX day4]$ touch soft{1..10}.exe      ; ফাইল তৈরি সাথে Extension সহ। 
[student@hostX day4]$ ls                           ;  আউপুট দেখার জন্য 'ls' কমান্ড
[student@hostX day4]$ touch file{5,6,a,b}          ; ভ্যারিয়েবল ব্যবহার করে ফাইল তৈরির কমান্ড। 
[student@hostX day4]$ ls                           ;  আউপুট দেখার জন্য 'ls' কমান্ড
[student@hostX day4]$ touch file-{sakib,tamim,liza}          ; ভ্যারিয়েবল ব্যবহার করে ফাইল তৈরির কমান্ড। 
[student@hostX day4]$ ls                            ;  আউপুট দেখার জন্য 'ls' কমান্ড


[student@hostX day4]$ mkdir -p dir1/linux/redhat ; ডিরেক্টরি পাথ তৈরির কমান্ড। (-p = parent)
[student@hostX day4]$ ls dir1                    ; 'dir1' এর কন্টেন্ট দেখার কমান্ড। 
 linux
[student@hostX day4]$ touch dir1/linux/centos    ; ডিরেক্টরি পাথে ফাইল তৈরি কমান্ড। 
[student@hostX day4]$ cd dir1/linux/                    ;  ডিরেক্টরি পাথে প্রবেশ করার জন্য। 
[student@hostX linux]$ ls                             ; বর্তমান ডিরেক্টরির মধ্যে কি আছে সেটা দেখার জন্য। 
  centos  redhat         
[student@hostX linux]$ pwd                           ; আমরা কোথায় অবস্থান করিছি সেটা দেখার কমান্ড। 
  /home/student/linux21/day4/dir1/linux


[student@hostX linux]$ cd /home/student/linux21/day4  ; রুট পার্টিশন (/) হয়ে 'day4' ডিরেক্টরিতে প্রবেশ করার জন্য। 


or


[student@hostX linux]$ cd ../../         ; দুই ধাপ পিছনে (Parent) ডিরেক্টরিতে যাওয়ার কমান্ড। 
[student@hostX day4]$ rm -rf *           ; বর্তমান ডিরেক্টরির সকল ফাইল/ডিরেক্টরি কনটেন্ট রিমুভ করার জন্য। 
[student@hostX day4]$ ls                 ; কিছু আছে কিনা দেখার জন্য। 


########################################################
##################### Session :03 ######################
########################################################


Working with Hidden file/dir:
----------------------------
[student@hostX day4]$ mkdir  .training       ; 'mkdir' দিয়ে একটি ডিরেক্টরি তৈরি করা হয়েছে, শুরুতে ডট (.) আছে। 
[student@hostX day4]$ touch  .csl            ; 'touch' দিয়ে একটি ফাইল তৈরি করা হয়েছে, শুরুতে ডট (.) আছে। 
[student@hostX day4]$ ls -l                  ; কোন আউটপুট দেখা যাবে না। 


লিনাক্সে কোনও ফাইল/ডিরেক্টরির শুরুতে ডট (.) দিয়ে তৈরি করে সেটা লুকায়িত (Hidden) অবস্থায় থাকে। আর লুকানো ফাইল/ডিরেক্টরি 'ls' কমান্ড দিয়ে পাওয়া যায় না। এইজন্য 'ls' কমান্ডের সাথে '-a' অপশন ব্যবহার করতে হবে। 


[student@hostX day4]$ ls -la                     ; এখানে লুকানো ফাইল/ডিরেক্টরি দেখার জন্য '-a' অপশন ব্যবহার হয়েছে।  
===========================================================
= drwxrwxr-x. 3 student student 35 Apr 21 15:51 .         =
= drwxrwxr-x. 4 student student 31 Apr 21 15:35 ..          =
= -rw-rw-r--. 1 student student  0 Apr 21 15:51 .csl          =
= drwxrwxr-x. 2 student student  6 Apr 21 15:51 .training =
===========================================================
নোটঃ উপরের আউটপুটে আমাদের তৈরি করা '.csl' এবং '.training' ফাইল এবং ডিরেক্টরি দুইটি দেখা যাচ্ছে। সাথে আরও ২টি লুকায়িত ডিরেক্টরি দেখা যাচ্ছে। প্রথমটি সিংগেল ডট (.) যেটা বর্তমান (Current) ডিরেক্টরি হিসেবে বিবেচিত হয় এবং পরেরটি ডাবল ডট (..), যেটা প্যারেন্ট (parent) বা পূর্বের ডিরেক্টরি হিসেবে বিবেচিত হবে। 


 ; লুকানো (Hidden) ফাইল/ডিরেক্টরি থেকে রেগুলার ফাইল/ডিরেক্টরিতে নিতে চাইলে এটাকে rename করতে হবে। আর 'rename' করার জন্য 'mv' কমান্ড ব্যবহার হয়। 


[student@hostX day4]$ mv .training training         
[student@hostX day4]$ ls


নোটঃ লুকানো (Hidden) ফাইল/ডিরেক্টরিকে রেগুলার  ডিরেক্টরি/ফাইলে রূপান্তর করা জন্য, 'mv' কমান্ড ব্যবহার করা হয়। এক্ষেত্রে প্রথমে যে লুকানো (Hidden) ফাইল/ডিরেক্টরি থেকে রেগুলার ডিরেক্টরিতে রুপান্তর করা হবে, সেটার নাম (.training) প্রথমে দিতে এবং যে নামে (নতুন) করা হবে সেটা পরে দিতে হবে। এক্ষেত্রে আমরা একই নাম (training) রাখতে পারি বা নতুন নাম (teaching) দিতে পারি। 


আবার রেগুলার ফাইল/ডিরেক্টরিকে থেকে 'mv' কমান্ড দিয়ে লুকানো (Hidden) ফাইল/ডিরেক্টরি হিসেবে ব্যবহার করা যাবে। সেক্ষেত্রে প্রথমে রেগুলার ফাইলের নাম এবং শেষে ডট (.) সহ লুকানো (hidden) ফাইলের নাম দিতে হবে। 


########################################################
##################### Session :04 ######################
########################################################


Working with File/Directory Properties:
---------------------------------------
যখন উইন্ডোজ অপারেটিং সিস্টেমে কোনো ফাইল/ডিরেক্টরি সম্পর্কে বিস্তারিত জানার দরকার হয়, তখন  ডিরেক্টরির উপরে মাউচের ডান বাটন প্রেস করে 'Properties' থেকে বিস্তারিত তথ্য পাওয়া যায়। যেমনঃ সিকিউরিটি, সাইজ, টাইপ, মোডিফাই/আপডেট তারিখ, ভার্শন ইত্যাদি। 


[student@hostX day4]$ touch file1    ; 'touch' দিয়ে একটি ফাইল তৈরি করা হয়েছে। 
[student@hostX day4]$ mkdir dir1     ; 'mkdir' দিয়ে একটি ডিরেক্টরি তৈরি করা হয়েছে। 


[student@hostX day4]$ ll         ; লিনাক্সে 'll' কামান্ড ব্যবহার করে ফাইল/ডিরেক্টরির বিস্তারিত তথ্য (Properties) দেখা যাবে। 


 d   rwx rwx  r-x .   2   student student   6         Feb  4 18:06         dir1
 -   rw- rw-  r-- .   1   student student   0         Feb  4 18:06         file1


(1)  2a  2b   2c 2d   3      4      5       6             7                  8


 1: file/dir types (লিনাক্সে মোট সাত ধরনের (-, d, l, c, b, s, p) ফাইল/ডিরেক্টরি পাওয়া যাবে) 
 2: file/dir পার্মিশন ফিল্ড এবং এখানে ডট (.) সহ মোট ১০টি ক্যারেক্টার আছে। এই দশটি ক্যারেক্টার কে আবার ৪ টি আলাদা ফিল্ডে ভাগ করা হয়েছেঃ 
        2a: user permission, 
        2b: group permission, 
        2c: others permission 
        2d: ACL Permission (.)


 3: file/dir link (Hard Link) - ফাইলের ক্ষেত্রে '1' আর ডিরেক্টরির ক্ষেত্রে '2' থাকবে, তবে ভিতরে যত ডিরেক্টরি থাকবে তার উপরে ভিত্তি করে সংখ্যা বাড়বে। 
 4: file/dir owner (যে ইউজার ফাইল/ডিরেক্টরিটি তৈরি করেছে তার নাম থাকবে) 
 5: file/dir group owner - (ইউজার যে গুরুপের সদস্য সেই গ্রপের নাম থাকবে) 
 6: file/dir size (byte) - ফাইল হলে '0' বাইট এবং ডিরেক্টরি হলে 6 বাইট (XFS) ফাইল সিস্টেমে। 
 7: file/dir modify date - তৈরির বা আপডেটের তারিখ এবং সময়। 
 8: file/dir name        - ফাইল বা ডিরেক্টরির নাম।  


 FIle/dir Permission:
 ---------------------------
 r = read
 w = write
 x = execute
 - = no permission
 . = ACL File Permission (+)


Linux File & Directory types:
-----------------------------  
 - = Regular file      : text/any file
 d = Directory         : Regular directory (ফোল্ডার) 
 l = Link file         : $ ls -l /dev/stdin 
 b = Device CD/DVD/HDD : $ ls -l /dev/sda
 c = Character device  : $ ls -l /dev/tty 
 s = Socket            : $ ls -l /run/rpcbind.sock   
 p = Pipe file         : $ ls -l /run/initctl      
 
b - Block Devices (CD/DVD/ISO/HDD/USB)
c - printer, sound card, virtual terminal, serial port, parallel port
l - link file (softlink/symbolik link)
s - A socket file is used to pass information between applications/process for communication purpose
p - Pipe Files. Multiple processes can access this special file for reading and writing


[student@hostX day4]$ cd /dev
[student@hostX dev]$ ll
[student@hostX dev]$ cd -  
[student@hostX day4]$ cd /run
[student@hostX run]$ ll
[student@hostX run]$ cd -
[student@hostX day4]$ 


Copy/Paste/Remove/Rename/Delete
===============================
[student@hostX day4]$ ls          ; 'ls' কমান্ড দিয়ে দেখা যাচ্ছে 'fiel1' এবং 'dir1' নামে একটি করে ফাইল এবং ডিরেক্টরি আছে। 
 file1 dir1
[student@hostX day4]$ cp file1 file2         ; ফাইল কপি করার জন্য 'cp' কমান্ড ব্যবহার করে 'file1' টি কপি করে 'file2' নামে আরেকটি করা হয়েছে। 
[student@hostX day4]$ ls
[student@hostX day4]$ cp file1 /home/student        ; ফাইল কপি করে অন্য লোকেশনে '/home/student' একই নামে। 
[student@hostX day4]$ cp file1 /home/student/file3  ; ফাইল কপি করে অন্য লোকেশনে '/home/student' অন্য নামে।  
[student@hostX day4]$ cd /home/student              ; '/home/student' লোকেশনে ঢুকে দেখা হয়েছে কপি হয়েছে কিনা। 
[student@hostX ~]$ ls
file1
file3
[student@hostX ~]$ cd -
[student@hostX day4]$ cp /etc/passwd .      ; অন্য লোকেশন থেকে ফাইল কপি করে বর্তমান ডিরেক্টরির (.) মধ্যে নিয়ে আসার কমান্ড। 
[student@hostX day4]$ ls                    ; কপি হয়ে আসছে কিনা সেটা দেখার জন্য। 
[student@hostX day4]$ cp /etc/hostname  /home/student  ; বর্তমান ডিরেক্টরিতে থেকে অন্য ডিরেক্টরির ফাইল কপি করে অন্য লোকেশনে পাঠানোর কমান্ড।  
[student@hostX day4]$ cd /home/student
[student@hostX ~]$ ls
[student@hostX ~]$ cd -                  ; পূর্বের ডিরেক্টরিতে ফিরে যাওয়ার কমান্ড। 
[student@hostX day4]$ cp dir1 dir99      ; wrong command
[student@hostX day4]$ cp -r dir1 dir99   ; ডিরেক্টরি কপি করার জন্য অবশ্যই 'cp -r' ব্যবহার করতে হবে। (-r = recursively)
[student@hostX day4]$ cp -r /etc .       ; '/etc' ফুল ডিরেক্টরি কপি করে বর্তমান ডিরেক্টরির (.) মধ্যে নিয়ে আসার কমান্ড। 
[student@hostX day4]$ ls 
[student@hostX day4]$ mv file2 file4     ; 'mv' কমান্ড দিয়ে ফাইল 'file2' কে 'file4' নামে পরিবর্তন করা হয়েছে। 
[student@hostX day4]$ ls                 ; এখানে দেখা যাচ্ছে 'file2' নাম পরিবর্তন করে 'file4' নামে হয়েছে।     
[student@hostX day4]$ mv file4 /home/student     ; ফাইল মুভ (cut) করে অন্য লোকেশনে নিয়ে যাওয়া। 
[student@hostX day4]$ ls                 ; বর্তমান ডিরক্টরির মধ্যে 'file4' নামে কিছু পাওয়া যাবে না। কারন এটা '/home/student' মধ্যে                                                                পাঠানো হয়েছে। 
[student@hostX day4]$ rm file1           ; ফাইল মুছে ফেলার জন্য 'rm' কমান্ড। 
[student@hostX day4]$ ls                 ; ফাইল টি নাই (deleted) 
[student@hostX day4]$ rm dir99        ; wrong command (শুধু 'rm' কমান্ড দিয়ে ডিরেক্টরি রিমুভ করা যাবে না)। 
[student@hostX day4]$ rm -r dir99     ; ডিরেক্টরি রিমুভ করার জন্য অবশ্যই '-r' ব্যবহার করতে হবে। (-r =  recursively)
[student@hostX day4]$ rm -r etc       ; সম্পূর্ণ ডিরেক্টরি রিমুভ করার জন্য প্রতিবার 'y' অপশন প্রেস করে কনফার্ম করতে হবে। 
 C^                                   


 'Ctrl + C' প্রেস করে, ফাইল রিমুভ বিরত রাখতে পারি। 


[student@hostX day4]$ rm -rf etc      ; প্রতিবার 'y' প্রেস করার পরিবর্তে '-rf' ব্যবহার করলে, একসঙ্গে সকল ফাইল/ডিরেক্টরি মুছবে।  
                                        (-f = forcefully, r=recursively)
[student@hostX day4]$ ls              ; 'etc' ডিরেক্টরি আছে কিনা দেখার জন্য। 
[student@hostX day4]$ rm -rf *                        ; বর্তমান ডিরেক্টরির সকল ফাইল/ডিরেক্টরি কনটেন্ট রিমুভ করার জন্য (*) ব্যবহার করা হয়। 
[student@hostX day4]$ ls              ; কিছুই পাওয়া যাবে না। 


 note: rm -rf * .*  লুকানো ফাইল (Hidden) সহ ডিলিট করার কমান্ড। 


 ===================== The End =======================