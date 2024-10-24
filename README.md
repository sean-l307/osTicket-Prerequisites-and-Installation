<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osticket-prereqs</h1>
"This tutorial walks you through the prerequisites and installation of osTicket, an open-source support ticketing system. It's designed for beginners to learn the basics, but in real-world scenarios, further customization may be needed to fit your company’s requirements. We'll be deploying osTicket on a Windows 10 virtual machine (VM) hosted in Azure, though you can use any machine capable of running a VM. If you're unfamiliar with setting up a VM, a link to a previous tutorial with a step-by-step guide will be provided below."<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Remote Desktop
- Internet Information Services
- osTicket
- HeidiSQL

<h2>Operating Systems Used </h2>

Windows 10 (21H2)

<h2>Installation Steps</h2>


![Capture3](https://github.com/user-attachments/assets/08c3a690-3dee-4e6f-8b9f-92d8c1c1d309)


<p>
"First, we'll connect to the virtual machine (VM) using Remote Desktop Connection (RDC). To do this, navigate to the VM in the Azure Portal, copy the Public IP address, and use it to connect via RDC."
</p>
<br />


![Capture4](https://github.com/user-attachments/assets/b1df73f8-9feb-40e1-86de-ad398ae42b54)


<p>
After downloading the osTicket-Installation-Files.zip, unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
</p>
<br />

<p float="left">
  <img src="https://github.com/user-attachments/assets/5cced2df-21d9-41e8-85af-69868175c452" alt="Capture5" width="70%" />
  <img src="https://github.com/user-attachments/assets/5338e6eb-d129-406f-ae29-3453dbb5bb1b" alt="Capture6" width="70%" />
</p>

</p>
<p>
Then, proceed to install IIS in Windows and enable CGI by navigating to World Wide Web Services > Application Development Features, and checking the box for CGI."
</p>
<br />

<p float="left">
  <img src="https://github.com/user-attachments/assets/2cc74cfe-dff8-4e91-9c80-51ec5cc4cdbb" alt="Capture8 1of2" width="70%" />
  <img src="https://github.com/user-attachments/assets/d05b6606-2782-43ec-bcbd-b4d5b03b0932" alt="Capture8 2of2" width="45%" />
</p>
<p>

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>
<br />


![Capture9p2](https://github.com/user-attachments/assets/2432a013-8684-4521-9ac0-217f5f210edd)
After creating the directory C:\PHP, from the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
![Capture10](https://github.com/user-attachments/assets/c5097a1f-b0bb-4580-b8d9-e17e40cf753b)

  
</p>
<p>

Then from the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
</p>
<br />


![Capture11(not needed but if u want to put it)](https://github.com/user-attachments/assets/5b4d4eb0-63a2-4588-8412-607e8158c0fc)

</p>
<p>
 
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Then make a secure password with a mix of upper and lowercase letters, numbers, and special characters

</p>
<br />
