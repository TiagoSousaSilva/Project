```
#Ubuntu Server In AWS

sudo systemctl stop ntp
sudo apt-get remove ntp
sudo apt-get install chrony
sudo systemctl start chrony
sudo systemctl enable chrony
sudo systemctl status chrony

sudo nano /etc/chrony/chrony.conf

// add the following:

pool 0.pt.pool.ntp.org iburst
allow 192.168.1.0/24 // example

//And Remove All The Pools

timedatectl set-ntp true
sudo systemctl restart chrony

//TroubleShoot

ss -ulnp  // Look for port 123  
chronyc sources -v
chronyc clients -v

```

```
#Ubuntu Client In AWS

sudo systemctl stop ntp
sudo apt-get remove ntp
sudo apt-get install chrony
sudo systemctl start chrony
sudo systemctl enable chrony
sudo systemctl status chrony

sudo nano /etc/chrony/chrony.conf

//Add The Following To The End Of The File:

server 10.0.0.13 // Server IP
server master iburst

//Remove All The Pools And Uncomment The Following:

log tracking measurements statistics

// Comment The Following:

#confdir /etc/chrony/conf.d
#sourcedir /run/chrony-dhcp
#sourcedir /etc/chrony/sources.d
#leapsectz right/UTC


timedatectl set-ntp true
sudo systemctl restart chrony


//Check If It's Working

timedatectl 

               Local time: Tue 2023-03-28 10:33:01 UTC
           Universal time: Tue 2023-03-28 10:33:01 UTC
                 RTC time: Tue 2023-03-28 10:33:01
                Time zone: Etc/UTC (UTC, +0000)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
          
chronyc sources

MS Name/IP address         Stratum Poll Reach LastRx Last sample               
===============================================================================
^? 169.254.169.123               3   4     1     1    +16us[  +16us] +/-  624us
^? 10.0.0.13                     4   6     1     1   -267us[ -267us] +/-   63ms
          

```

```
#Help

https://www.layerstack.com/resources/tutorials/How-to-install-Network-Time-Sync-NTP-with-Chrony-on-Ubuntu20

https://www.server-world.info/en/note?os=Ubuntu_22.04&p=ntp&f=2

https://www.ibm.com/docs/en/db2/11.1?topic=suntp-setting-up-chrony-as-network-time-protocol-server-client-by-using-chronyd-linux
