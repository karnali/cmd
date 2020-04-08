# List of frequently used commands. Linux, macOS, awscli ...

Disk Free (df) 
```
$ sudo df -h .; sudo du -sh /var/lib/docker 
```
Disk Use(du)
```
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

# AWS s3
Backup cloud9 environment to s3
```
$ aws s3 cp /home/ubuntu/environment/ s3://bucketname/ --recursive
$ aws s3 sync /home/ubuntu/environment/ s3://bucketname/
```
Cronjob [min,hr,dayofmonth1-31,month,dayofweek sun0-6]
```
0 7 * * 1 aws s3 cp /home/ubuntu/environment/ s3://bucketname --recursive
```


Protect your Cloud9 data. From Cloud9 terminal.

Create s3 bucket
----------------
aws s3 mb s3://environment --region us-east-1

Backup Cloud9 environment
--------------------------
aws s3 sync ~/environment s3://environment

Restore Cloud9 environment
--------------------------
aws s3 sync s3://environment  ~/environment

List s3
--------
aws s3 ls
