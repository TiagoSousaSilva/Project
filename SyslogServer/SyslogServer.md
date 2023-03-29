```
#Syslog Server Configuration

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

