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
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
