https://phoenixnap.com/kb/openvpn-centos

ec2-user@ip-192-168-0-10 ~$ sudo -s
root@ip-192-168-0-10 ec2-user# yum install epel-release -y
Last metadata expiration check: 23:30:05 ago on Thu Mar 30 09:11:18 2023.
No match for argument: epel-release
Error: Unable to find a match: epel-release
root@ip-192-168-0-10 ec2-user# yum install -y openvpn
Last metadata expiration check: 23:30:21 ago on Thu Mar 30 09:11:18 2023.
No match for argument: openvpn
Error: Unable to find a match: openvpn
root@ip-192-168-0-10 ec2-user# yum install -y wget
Last metadata expiration check: 23:30:39 ago on Thu Mar 30 09:11:18 2023.
Package wget-1.21.3-1.amzn2023.0.2.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!
