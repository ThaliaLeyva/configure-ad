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

- Create Virtual Machine containing active directory within Azure
- Create second Virtual Machine to be used as a "client" within Azure
- Join "User or Client" Virtual Machine to the domain
- Create User accounts using powershell

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/8Md3axE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create virtual machinces within Azure to be utilized as the domain controller containing active directory.
It is important to set the IP address to static of the Virtual Machine that will serve as the domain controller to ensure the IP address will not change.

</p>
<br />

<p>
<img src="https://i.imgur.com/2gjGN8z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a second Virtual Machine to be used as a client of the domain. To ensure connectivity between the two vitrual machine we will test using ping. obtain domain controllers private IP address and open command line through client 1 to ping virtual machine acting as domain controller. The ping will fail, access Domain Controller via remote destktop and configure firewall to allow traffic from ICMP then permitting communication between the two virtual machines.
</p>
<br />

<p>
<img src="https://i.imgur.com/9tG999g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After installing active directory onto the domain controller, it is important to join client 1 to the same network. In order to do so you must access the network congfigurations of the virtual machine acting as client, then set custom DNS Server to the IP Address of the Domain Controller. 
</p>
<br />

<p>
<img src="https://i.imgur.com/LH05K74.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then logging in as the client you will want to set the system properties to allow access into Domain Control via remote desktop of all users within the security group. After doing so log into Domain control as one of the user profiles opening powershell as an administrator. Create a new file and paste the given script into the file and run, by doing so it will create however many said accounts. The new user accounts will be put into the designated folder and displayed. Essentially you will be able to select any new user account and log into domain control.
</p>
<br />
