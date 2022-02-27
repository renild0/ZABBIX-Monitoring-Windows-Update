# ZABBIX-Monitoring-Windows-Update
Tested on Zabbix 4.0.x | Windows Server 2019 Datacenter (EN) | PowerShell

Windows Update Monitoring Template

Tested on Windows Server 2019 Datacenter (EN)

First step: Create a folder called Scripts inside C:\Program Files\Zabbix Agent\ or wherever you like.

Copy the CountUninstalle Updates.ps1 file to C:\Program Files\Zabbix Agent\Scripts\

Second step: Change the lines in the zabbix_agentd.conf file

Timeout=30 UnsafeUserParameters=1 EnableRemoteCommands=1

And add the UserParameter line: UserParameter=CountUninstalledUpdates,powershell -NoProfile -ExecutionPolicy bypass -File "C:\Program Files\Zabbix Agent\Scripts\CountUninstalledUpdates.ps1"

Third step: Access the Zabbix Front: Add the Template to the host and restart the Agent service on the monitored client.


![image](https://user-images.githubusercontent.com/88397673/155885516-4f15a038-6d5a-49a9-a140-93c9fe2a1e0c.png)
