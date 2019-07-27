## Basic commands:

```ansible server -m ping```<br />
```ansible nodes -m ping```<br />
```ansible all -a "free -m"```<br />
```ansible all -a "uptime"```<br />
```ansible server -a "service httpd status"```<br />
```ansible server -a "ps -fC httpd"```<br />
```ansible nodes -a "reboot"```<br />
```ansible server -m service -a "name=httpd state=started"```<br />
```ansible server -m service -a "name=httpd state=stopped"```<br />
```ansible server -m service -a "name=httpd state=reloaded"```<br />
```ansible server -m service -a "name=httpd enabled=yes"```<br />
```ansible server -m service -a "name=httpd enabled=no"```<br />
```ansible server -m copy -a "src=/etc/hosts dest=/root mode=0644"```<br />
```ansible nodes -m copy -a "src=/etc/hosts dest=/etc/hosts mode=0644"```<br />
```ansible server -m file -a "path=/etc/hosts mode=0644" ```<br />
```ansible all -m file -a "path=/etc/hosts mode=0654"```<br />
```ansible all -m file -a “path=/etc/hosts hosts state=file”```<br />
```ansible all -m file -a “path=/tmp/testfile state=absent”```<br />
```ansible all -m yum -a "name=whois state=latest"```<br />
```ansible all -m yum -a "name=whois state=present"```<br />
```ansible all -m yum -a "name=whois state=absent"```<br />
```ansible server -m yum -a “upgrade=yes” -u root```<br />
```ansible all -m yum -a “name=whois state=latest” -u root```<br />
```ansible nodes -m fetch -a “src=/etc/hosts dest=/tmp”```<br />
```ansible server -a "crontab -l"```<br />
```ansible server -m cron -a "name=Update job=ntpdate in.pool.ntp.org state=present"```<br />
```ansible server -m sysctl -a "name=vm.drop_caches state=absent"```<br />
```ansible all -m user -a "name=media uid=10000 shell=/bin/bash"```<br />
```ansible all -m user -a "name=media state=absent"```<br />
```ansible all -m group -a "name=projectx gid=6000 state=present"```<br />
```ansible all -m group -a "name=projectx state=absent"```<br />
```ansible server -m file -a "path=/tmp/temp_logs.log state=touch"```<br />
