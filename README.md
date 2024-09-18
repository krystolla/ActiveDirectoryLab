<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
This repository shows how I walked through to create an Active Directory home lab Environment using Oracle VirtualBox. Configuring and running this lab will help develop understanding of how active directory and windows networking works.

<h2>Project Overview</h2>

<b>This project demonstrates the following:</b> 
- Installing and configuring Active Directory on a Windows Server VM.
- Creating users and managing them using PowerShell scripts. 
- Automating user creation and management in Active Directory.
  
<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>
 
<h2>Program walk-through</h2>

<p align="center">
<img src="https://i.imgur.com/s10gO3M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<b>Network and Virtual Machine Overview</b>
 
1.	Install 2 separate virtual machines: Active Directory Domain controller (DC) / Private virtual machine (Client1)
2.	DC (Server 2019 ISO): Create more than 1,000 users in Active Directory Using Powershell.
3.	Client1 (Windows 10 ISO): Communicate with the DC to authenticate users, retrieve policies, and interact with other domain resources.
4.	Internet Connection: The Internet connection for the DC is handled by DHCP.

<b>Network Interfaces and IP Configuration</b>

1.	DC - NIC (INTERNET): Gets IP address from the home router using DHCP. It is responsible for the server’s connection to the external network (the internet).
2.	DC - NIC (Internal): IP Address: 172.16.0.1 / Subnet Mask: 255.255.255.0 / DNS: 127.0.0.1 / Gateway: No gateway. Isolated for internal communication.
3.	Client1 - NIC (Internal): The client gets its IP address automatically from the DC via DHCP. This NIC is part of the internal network and will communicate with the Domain Controller for services like domain joining, user authentication, and receiving group policies.

<br />
<br />
Create users in Active Directory using Powershell: <br/>
<img src="https://i.imgur.com/ya3iv7D.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Example of Find Users: <br/>
<img src="https://i.imgur.com/Tgqs13t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Address Leases: <br/>
<img src="https://i.imgur.com/cVwG38h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
User kson’s Successful Domain Login and Network Configuration Check: <br/>
<img src="https://i.imgur.com/fudqM3n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
