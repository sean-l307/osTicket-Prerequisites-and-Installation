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
Then make a secure password with a mix of upper and lowercase letters, numbers, and special characters.

</p>
<br />

<p float="left">
  <img src="https://github.com/user-attachments/assets/631272df-0479-4e10-b519-8d2b185bd352" alt="Capture12" width="45%" />
  <img src="https://github.com/user-attachments/assets/800de62e-dc15-4f2f-941d-6f3225df0e22" alt="Capture12_1" width="45%" />
</p>
<p>
Open IIS as an Admin then register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe).Finally reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p float="left">
  <img src="https://github.com/user-attachments/assets/1e799fb4-c4a2-4527-8d66-5a7acfcbca89" alt="Capture14edit" width="45%" />
  <img src="https://github.com/user-attachments/assets/66dae89c-a4e4-4173-b8aa-499ef9d9286f" alt="Capture14image" width="45%" />
</p>
<p>
"Download the osTicket-v1.15.8 file from the installation folder. Once it's downloaded, open two file explorer windows. In one window, navigate to the osTicket-v1.15.8.zip folder, and in the other, go to 'inetpub' > 'wwwroot.' Extract the 'upload' folder from the osTicket zip and move it to the 'wwwroot' directory. Once the transfer is complete, rename the 'upload' folder to 'osTicket'."
</p>
<br />


![image](https://github.com/user-attachments/assets/aaeac803-5a21-4a66-9baa-924ea7df87b3)
![image](https://github.com/user-attachments/assets/cfd495df-ff2e-4541-8cfa-225bfba65d66)

</p>
<p>
Restart IIS as admin and expand VM1 on the left menus > Sites > Default Web Sites > Click osTicket. Click on "Browse *.80 which will open web browser that will open a osTicket installer.
</p>
<br />

<p>
    <img src="https://github.com/user-attachments/assets/f38f8a03-cde2-4f80-a924-6afe503d0905" alt="Image 1" style="display:inline-block; margin-right:10px;" width="500">
    <img src="https://github.com/user-attachments/assets/dabb8598-1334-4c79-911a-cf7fb2c57e36" alt="Image 2" style="display:inline-block;" width="500">
</p>
<p>
Return to IIS Manager and navigate back to osTicket. Click on the 'PHP Manager' icon, then scroll to the bottom and select 'Enable or disable an extension.' Enable the extensions 'php_imap.dll', 'php_intl.dll', and 'php_opcache.dll' by right-clicking on each and selecting 'Enable.
</p>
<br />

![Capture16part2](https://github.com/user-attachments/assets/1ef5b895-eff0-4ba3-a8bb-44c58d4fd4da)
</p>
<p>
Refresh the web browser that has the osTicket installer and observe the changes. It should look like the screenshot above.
</p>
<br />

<p>
    <img src="https://github.com/user-attachments/assets/b6fbd1f3-9cdd-413c-b96b-7575dca0fbf2" alt="Image 1" style="display:inline-block; margin-right:10px;" width="500">
    <img src="https://github.com/user-attachments/assets/b01270f8-c70f-418b-a8f3-c373289e8d51" alt="Image 2" style="display:inline-block;" width="500">
</p>
<p>
Open File Explorer and navigate back to the osTicket folder within inetpub. Click on the 'include' directory and find ost-sampleconfig.php at the bottom of the list. Rename the file from ost-sampleconfig.php to ost-config.php.
</p>
<br />


![image](https://github.com/user-attachments/assets/1969d559-fb96-4fb3-89ab-3bd97996d64d)
</p>
<p>
Next, right-click on the file and select Properties. Go to the Security tab, then click on Advanced. Disable inheritance and remove all entries.(In most real life situations your not gonna allow all these) 
</p>
<br />


![Capture17](https://github.com/user-attachments/assets/c6434fa2-c90d-43c8-9231-824349f70d45)
</p>
<p>
After that, click Add, then select a principal. Type 'Everyone' in the object box, click Check Names, and then press OK.
</p>
<br />

![Capture17part2](https://github.com/user-attachments/assets/b4ba736e-9b76-4de2-9331-0f31386b72ba)
</p>
<p>
Check the box for 'Full Control,' then click OK. Apply the changes and continue clicking OK until the Properties window closes.
</p>
<br />


![Capture18(might have sc'ed to early)](https://github.com/user-attachments/assets/3170e37a-16f2-46eb-aa03-69e61b0862c2)
</p>
<p>
Go back to the osTicket installer and click 'Continue.' Then, select a name for your helpdesk and provide a random email address. For this tutorial, we'll use the name 'Sean's Help Desk' and the email '(enter an email).' Next, create your own admin user credentials. I used a random email and set a password, so make sure to jot these down for future reference.
</p>
<br />


![Capture19(set up databse)](https://github.com/user-attachments/assets/746d0db6-7790-4e1b-8077-4fcd1f058ec8)
</p>
<p>
Next, download HeidiSQL from the drive folder that contains a Word document with the download link. Open the installer and click 'Continue' until the installation is complete. Once installed, click the 'New' button at the bottom of the window. The username should be pre-filled as 'root'; enter the password we created, 'Password1,' and then click 'Open. In HeidiSQL, right-click on 'Unnamed,' then select 'Create New' followed by 'Database.' Name the new database 'osTicket' and click OK.
</p>
<br />


![Capture19(input info on databse)](https://github.com/user-attachments/assets/681bd2f4-5a58-4382-89db-e666a865cc2d)
</p>
<p>
Return to the osTicket installer and enter the username and password. Use 'root' for the username and 'Password1' for the password. The hostname should also be set to 'osTicket.
</p>
<br />


![image](https://github.com/user-attachments/assets/f13b54a3-a570-4a34-9b5d-8bdd9f8131fe)
</p>
<p>
To tidy up the tutorial, navigate back to C:\inetpub\wwwroot\osTicket and delete the 'setup' folder.
</p>
<br />


![image](https://github.com/user-attachments/assets/c7dba648-c966-452c-8107-5e4b64bf7ab0)
</p>
<p>
Stay in the osTicket folder and navigate to the 'include' directory. Locate 'ost-config.php,' right-click on it, and select Properties. Go to the Security tab, then click on Advanced. Select 'Everyone,' click Edit, and set the permissions to 'Read' and 'Read and execute' only. Click OK, then Apply, and finally OK to close the window.
</p>
<br />

