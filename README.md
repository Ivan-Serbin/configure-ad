<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Creation of resources in Azure; create a windows server and standard windows vm
- Step 2: Ensure connnectivity between Domain controller and Client; windows server(DC-1), standard windows account(client-1)
- Step 3: Install active directiory in DC
- Step 4: Create an Admin and standard user account in AD
- Step 5: Connect the Client vm to the domain (mydomain.com)
- Step 6: Setup Remote Desktop for non-admin users on Client-1
- Step 7: Create users in AD in DC and atempt to login on Client-1 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/0cqP08m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First login to Microsoft Azure, then make your way to virtual machines > create > azure virtual machine > create new resource group (ADlab) > name the machine DC-1 > select your appropirate region (must be the same for both vm's) > select windows server 2022 > select however much vcps and GiB memory you think you will need (in general more vcpu and GiB means a faster vm) > create a username and password > confirm the licensing box and create the vm. The steps for creating the Client-1 vm are the same with the exception of the step where you choose the image, which should be windows 10 pro. 
</p>
<br />

<p>
<img src="https://i.imgur.com/lzlx2N9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next you want to make sure to set the ipv4 address of the DC to static. In order to do this go to virtual machines > DC-1 > networking > click on dc-1378 next to network interface > ip configurations > ipconfig1 > change assignmetn from dymanic to static > save. Now that the network is static it will make it possible for the Client-1 to connect to the domain using the DNS of the static ipv4 from DC-1.
</p>
<br />

<p>
<img src="https://i.imgur.com/EzUD5H6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into Client-1 with remote desktop connection > windows > cmd > type ping -t [static ip address]. This will perpetually be pinging the DC-1 server. However you will notice that it's coming back as request timed out, meaning that we need to enable ICMPv4 in the firewall of DC-1 to let this traffic through.
</p>
<br />

<p>
<img src="https://i.imgur.com/laEhaWW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/yqRUaZt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Log into DC-1 with remote desktop connection > windows > firwall security settings > Advanced settings > inbound/outbound rules to allow "IPV4 permissions" on DC-1's Firewall. This will open the firewall for connectivity after DC-1 is converted into a domain. Now just switch back to Client-1 to make sure that the requests are going through.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next is going to be installing active directory on DC-1. For this you will need to go to server manager dashboard > add roles and features > Click next until you get to the option to add Active Directory Domain Service > continue without any changes until you get to install AD > a yellow flag will apear in the top right corner, click on that > promote this server to domain controller > add new forest [mydomain.com] > create a password for the root user > go untiol you can install AD > restart DC-1 > login as mydomain.com\[chosen name] or [choosen name]@mydomain.com
</p>
<br />

p>
<img src="https://i.imgur.com/BuNIduM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Now when logged into DC-1 as go to windows > Active Directory Users and Computers > 
</p>
<br />







