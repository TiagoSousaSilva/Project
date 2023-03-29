#SyslogServer Installation

```
https://www.manageengine.com/products/eventlog/on-prem-cloud-free-trial.html?utm_source=manageengine&utm_medium=referral&utm_campaign=syslog-server&utm_content=ela-header

//Enter terminal on GUI 

~/Downloads$ chmod 777 ManageEngine_EventLogAnalyzer_64bit.bin

/home/remnux/Downloads# ./ManageEngine_EventLogAnalyzer_64bit.bin 

/home/remnux/Downloads# service eventloganalyzer start

//Troubleshooting: If the website doesn't work:
//Open the 8400 port through the terminal (Default)

service eventloganalyzer start 
```

```
//Add linux users to EventLog

sudo -s

nano /etc/rsyslog.conf 

*.* @10.0.0.13:514

systemctl restart rsyslog

//Add Windows users to EventLog - http://[PublicIP]:8400/

In EventLog analyzer website go to: 

Settings -> Devices -> Windows Devices -> Add Device(s) -> Input the Windows Private IP
