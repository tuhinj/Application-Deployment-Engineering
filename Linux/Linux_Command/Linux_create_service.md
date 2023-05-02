HOW TO CREATE SERVICE IN LINUX
==============================
**Root user**
> sudo su 

or 

> sudo -i

*Enter password...*

**Check Services**
> systemctl --type=service

**Check Service Status, disable, enable, start, stop service**
> systemctl status 'AnyServiceName'

> systemctl disable 'AnyServiceName'

> systemctl enable 'AnyServiceName'

> systemctl start 'AnyServiceName'

> systemctl stop 'AnyServiceName'

**For create services, enter in '/etc/systemd/system' this directory**
> cd /etc/systemd/system

> ls 

*ls for showing services...*

**Create Service**
> nano create.service

***pest this flowing line***
[Unit]

Description = This will Create a new file

After = network.target

[Service]

ExecStart = /usr/local/bin/touch.sh

[Install]

WantedBy = multi-user.target

***save it***

*change mood*

> chmod a+x create.service

*enable service*

> sustemctl enable create.service

*create a bash script file '/usr/local/bin'*

> nano touch.sh

***pest this flowing line***

#!/bin/bash

touch /root/file

***save it***

*change mood*

> chmod a+x touch.sh

*start service*

> systemctl start create.service

			END
			===

