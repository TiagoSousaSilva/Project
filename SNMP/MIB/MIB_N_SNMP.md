#MIB

```
//Verify If Its Installed

sudo apt list libsnmp-base
libsnmp-base/focal-updates,focal-updates,now 5.8+dfsg-2ubuntu2.3 all [installed]
sudo apt-get install libsnmp-base

//If It Is:

sudo apt upgrade

// How to add devices:


```
#SNMP
```
#SNMP Server/Client Configuration

// Open Linux GUI and proceed to the following website:

https://www.manageengine.com/products/mibbrowser-free-tool/download.html

sudo /[Folder] // To install



// Enter the /bin folder and run the ./MibBrower.sh command

remnux@remnux:~/ManageEngine/ManageEngine_Free_Tools/MibBrowser_Free_Tool/bin$ ./MibBrowser.sh



//In the Server Terminal

sudo apt-get update

sudo apt-get install snmpd

sudo nano /etc/snmp/snmpd.conf



//Change the following:

agentAddress udp:161,udp6:[::1]:161

sudo service snmpd restart

sudo service snmpd status

```

```
# SNMP Client Configuration

sudo apt install snmpd snmp libsnmp-dev

sudo cp /etc/snmp/snmpd.conf /etc/snmp/snmpd.conf.bak

sudo nano /etc/snmp/snmpd.conf

//Change the following:

agentAddress udp:161

rocommunity public 10.0.0.13 //Tag the other rocommunities

sudo service snmpd restart

