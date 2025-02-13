<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Deployingg Active Directory</h1>
This tutorial outlines the implementation and deployment of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Active Directory Install
- Create a Domain Admin user within the domain
- Join Client-1 to your domain (mydomain.com)

<h2>Deployment and Configuration Steps</h2>

Login to DC-1 and install Active Directory Domain Services

Start -> Server Manager -> Add roles and features -> Next, Next, Next -> [X] Active Directory Domain Services -> Next, Next, Next, Install
</p>
<br />

<p>
<img src="https://i.imgur.com/gYwZs9Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)

Restart and then log back into DC-1 as user: mydomain.com\labuser
</p>
<br />

<p>
<img src="https://i.imgur.com/CFHjAyn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  
<img src="https://i.imgur.com/AkOGROR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called '_EMPLOYEES'
</p>
<br />
<p>
<img src="https://i.imgur.com/jmocH0T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new OU named "_ADMINS"
</p>
<br />
<p>
<img src="https://i.imgur.com/6HpI3iG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new employee named "Jane Doe" (same password) with the username of "jane_admin" / Cyberlab123!
</p>
<br />
<p>
<img src="https://i.imgur.com/Y1aN7HJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add jane_admin to the "Domain Admins" Security Group
</p>
<br />
<p>
<img src="https://i.imgur.com/pqRUN31.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log out / close the connection to DC-1 and log back in as "mydomain.com\jane_admin"

Use jane_admin as your admin account from now on
</p>
<br />
<p>
<img src="https://i.imgur.com/Y9KL8pC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
</p>
<br />
<p>
<img src="https://i.imgur.com/8a4UA70.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to the Domain Controller and verify Client-1 shows up in the ADUC
</p>
<br />
<p>
<img src="https://i.imgur.com/OnzKqge.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new OU named '_CLIENTS' and drag Client-1 into there
</p>
<br />
<p>
<img src="https://i.imgur.com/ZGF8Pbp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
