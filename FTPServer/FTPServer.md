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
listen=NO
listen_ipv6=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
dirmessage_enable=YES
xferlog_enable=YES
connect_from_port_20=YES
xferlog_std_format=YES
ascii_upload_enable=YES
ascii_download_enable=YES
chroot_local_user=YES
pam_service_name=vsftpd

add the following:

allow_writeable_chroot=YES
pasv_enable=YES
pasv_min_port=1024
pasv_max_port=1048
write_enable=YES
]

```

