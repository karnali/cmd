# Linux Commands

Disk Free (df) Disk Use(du)
```
$ sudo df -h .; sudo du -sh /var/lib/docker 

sudo du -a -h /var/lib/docker --max-depth=1 | sort -hr
```
Free Memory
```
free -m | grep "Mem:"
```
Netstat
```
$ netstat -tunlp
$ netstat -ano
```

Dig commands
```
$ dig google.com +noall +answer
$ dig -x 172.217.11.142 +noall +answer
```

SCP commands

Copy file from your desktop folder on your computer to server’s /tmp folder
```
scp linuxscp.txt user@serveraddress.com:/tmp/
scp -r linuxscp.zip user@serveraddress.com:/tmp/
```
Copy file from server’s /tmp folder to your desktop folder on your computer
```
scp user@serveraddress.com:/tmp/linuxscp.txt /Users/jsmith/Desktop/
scp -r user@serveraddress.com:/tmp/linuxscp.zip /Users/jsmith/Desktop/ 
```
Display config file without comments and spaces.
```
egrep -v '(^#|^\s*$)' 
egrep -v "^[[:space:]]*#|^$" httpd.conf-orig
egrep -v '(^#|^\s*$|^\s*\t*#)' httpd.conf-orig
```
