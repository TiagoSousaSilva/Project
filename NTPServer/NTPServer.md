```
#Ubuntu server

sudo apt update
sudo apt install ntp
sudo nano /etc/ntp.conf

// add the following:

server pool.ntp.org

sudo systemctl restart ntp
```
