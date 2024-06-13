<h1>Implementing a SOC and Honeynet in Azure</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
In this lab I setup a vulnerable virtual machine within Microsoft Azure to act as a honeypot to capture and log security events using the Microsoft Sentinel SIEM. I used a PowerShell script and a geolocation API to map where attacks originate from.
<br/><br/>
I first setup the VM and removed all safeties by allowing all traffic in the Network Security Group. I then connected to the VM via RDP and disabled the Windows Firewall on all profiles. This allows any outside party to see the host and try to login.
<br/><br/>
To capture the failed login attempts, I used a Powershell script to pull the latitude and longitude of the attacker from a free IP Geolocation API website. The script then saves this data to a custom log file on the Windows machine.
<br/><br/>
I then ingested that custom log into a Log Analytics Workspace in Azure and created a custom query to pull any further attempts from the VM. I connected my workspace to Microsoft Sentinel and setup a custom workbook to run the query every 5 minutes and visualize the data on a Map.
<br/><br/>

<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/482f0638-24d5-4756-be95-d82a24c57aba" height="80%" width="80%" alt="Resource Group"/>
<br/><br/>
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
<br />
<br />
Deploy the Windows 10 Virtual Machine:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/26ad5738-f85a-4c6c-9dad-bf6af51de258" height="80%" width="80%" alt="Virtual Machine"/>
<br />
<br />
Configure NSG to allow all traffic: <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/1daf6745-b7a6-4cc7-94de-e83186f60655" height="80%" width="80%" alt="Network Security Group"/>
<br />
<br />
RDP into machine:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/99213f3a-7dae-43e2-b970-4a676a553d31" height="80%" width="80%" alt="RDP into machine"/>
<br />
<br />
Disable host firewall:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/433b2d78-4aae-4b94-8ae2-cc456c151983" height="80%" width="80%" alt="Disable Host Firewall"/>
<br />
<br />
Geolocation API site:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/a39a80eb-95cd-430d-8302-99a7dd82f678" height="80%" width="80%" alt="Geolocation API site"/>
<br />
<br />
Edit Powershell script by adding API key:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/ece6c24c-c8b8-463d-9840-0ed7f9c8b477" height="80%" width="80%" alt="Edit Powershell script by adding API key"/>
<br />
<br />
Configure custom log to map to local disk of VM:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/c118afd4-73fa-4875-a74b-f0a4f8c2ea30" height="80%" width="80%" alt="Custom Log"/>
<br />
<br />
Connect Microsoft Sentinel to Workspace:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/0e7334a5-cb5e-483a-be6e-2ef41fa5d4f4" height="80%" width="80%" alt="Microsoft Sentinel Dashboard"/>
<br />
<br />
Setup Workbook query to visualize on map:  <br/>
<img src="https://github.com/ZakJaeb/SOC-Honeynet-Azure/assets/58833790/3ffc1977-eb0f-4539-aa02-3542f0bd98c8" height="80%" width="80%" alt="Workbook Query"/>
</p>
