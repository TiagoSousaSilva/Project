```
#Ubuntu Server

sudo apt update
sudo apt install ntp
sudo nano /etc/ntp.conf

// add the following:

server pool.ntp.org

sudo systemctl restart ntp
```

```
#Ubuntu Client

sudo apt-get update
sudo apt-get install ntp
sudo nano /etc/ntp.conf

//Add The Following To The End Of The File:

# Use your Ubuntu NTP server as the time source
server ubuntu-ntp-server  // Or the NTP Server IP

sudo systemctl restart ntp

//Check If It's Working
ntpq -p 

     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
 0.ubuntu.pool.n .POOL.          16 p    -   64    0    0.000   +0.000   0.001
 1.ubuntu.pool.n .POOL.          16 p    -   64    0    0.000   +0.000   0.001
 2.ubuntu.pool.n .POOL.          16 p    -   64    0    0.000   +0.000   0.001
 3.ubuntu.pool.n .POOL.          16 p    -   64    0    0.000   +0.000   0.001
 ntp.ubuntu.com  .POOL.          16 p    -   64    0    0.000   +0.000   0.001
 10.0.0.13       .INIT.          16 u    -   64    0    0.000   +0.000   0.001
 t1.time.bf1.yah 98.139.133.62    2 u    1   64    1   16.355   +1.127   0.001

```
