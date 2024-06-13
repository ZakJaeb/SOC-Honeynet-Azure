<h1>Implementing a SOC and Honeynet in Azure</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
In this lab I setup a vulnerable virtual machine within Microsoft Azure to act as a honeypot to capture and log security events using the Microsoft Sentinel SIEM. I used a PowerShell script and a geolocation API to map where attacks originate from.
<br/>
I first setup the VM and removed all safeties by allowing all traffic in the Network Security Group. I then connected to the VM via RDP and disabled the Windows Firewall on all profiles. This allows any outside party to see the host and try to login.

To capture the failed login attempts, I used a Powershell script to pull the latitude and longitude of the attacker from a free IP Geolocation API website. The script then saves this data to a custom log file on the Windows machine.

I then ingested that custom log into a Log Analytics Workspace in Azure and created a custom query to pull any further attempts from the VM. I connected my workspace to Microsoft Sentinel and setup a custom workbook to run the query every 5 minutes and visualize the data on a Map.

Thanks to Josh Madakor for the awesome lab project: https://www.youtube.com/watch?v=RoZeVbbZ0o0
<br />


<h2>Platforms and Technology Used</h2>

- <b>Azure Virtual Machines</b>
- <b>Microsoft Sentinel (SIEM)</b>
- <b>Log Analytics</b>

<h2>Environments Used </h2>

- <b>Azure Portal</b>
- <b>Powershell</b>

<h2>Project walk-through:</h2>

<p align="center">
Setup new resource group for lab: <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/e3e0702e-1635-4e62-aa86-3cf8cffbf22d" height="80%" width="80%" alt="Resource Group"/>
<!--
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
