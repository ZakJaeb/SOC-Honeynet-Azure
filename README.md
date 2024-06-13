<h1>Implementing a SOC and Honeynet in Azure</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
In this lab I setup a vulnerable virtual machine within Microsoft Azure to act as a honeypot to capture and log security events using the Microsoft Sentinel SIEM. I used a PowerShell script and a geolocation API to map where attacks originate from.

I waited until the next day and was

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
<!--
<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
