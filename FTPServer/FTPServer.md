Credit - https://www.hostinger.com/tutorials/how-to-setup-ftp-server-on-ubuntu-vps/

# FTPServer Config

Ubuntu - t2.small - 30Gb

// Start

Step 1 – Installing vsftpd

sudo apt-get update && sudo apt-get -y upgrade 

sudo apt-get install -y vsftpd | sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.original

Step 2 – Creating the User Directory

sudo adduser host

sudo mkdir /home/host/ftp

sudo chown nobody:nogroup /home/host/ftp

sudo chmod a-w /home/host/ftp

sudo ls -la /home/host/ftp

```
//Should show the following:

[
total 8
dr-xr-xr-x 2 nobody nogroup 4096 Oct 8 11:32 .
drwxr-xr-x 3 hostinger   hostinger 4096 Oct 8 11:32 ..
]
```

sudo mkdir /home/host/ftp/files

sudo chown host:host /home/host/ftp/files

echo "vsftpd sample file" | sudo tee /home/host/ftp/files/sample.txt

sudo nano /etc/vsftpd.conf

```
// Check the following:

[
# Allow anonymous FTP? (Disabled by default). 
anonymous_enable=NO 
# 
# Uncomment this to allow local users to log in. 
local_enable=YES
write_enable=YES
chroot_local_user=YES
]

```

