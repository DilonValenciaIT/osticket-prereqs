<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Vrtual Machine
- osTicket Installation files
- Heidi SQL
  


<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/df81e24f-e702-46f0-a5de-f906c70d4fbb)

<p>
Hello and welcome to my first step-by-step IT tutorial. To get started, creat an Azure Virtual Machine with a Windows 10 operating system and 4 vCPUS. In this case I'd name this VM the "osticket-vm". Using the username (labuser) and password (osTicketPassword1!). Place this in the "osTicket" Resource group. With the username and password, log into the VM with Remote Desktop Connection using the VM's IP address. Within the VM (osticket-vm), download osTicket-Installation-Files.zip (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it into the desktop. The folder should be called “osTicket-Installation-Files”. We will use the files in this folder to install osTicket and some of the dependencies.
</p>
<br />

![image](https://github.com/user-attachments/assets/23d21404-8641-45af-92f8-8461eb400846)

<p>
Up next, install and enable IIS (Internet Information Services) in Windows with CGI (World Wide Web Services > Application Development Features > [X] CGI). To do this, open the Control Panel. From there, select "Uninstall Programs", on the left select "Turn Windows feature on or off, once inside select "Internet Informaton Services", then expand to unveil "World Wide Web Services", from there we expand "Application Development Features", then finally we select "CGI", then hit OK. This will install the Web Server so that the IIS (127.0.0.1) is operational.  
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi). From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi). Create the directory "C:\PHP". 
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder. From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe. From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Typical Setup ->Launch Configuration Wizard (after install) ->Standard Configuration ->Username: root Password: root. Open IIS as an Admin. Register PHP from within IIS (PHP Manager--> Register new PHP version -> C:\PHP\php-cgi.exe). Reload IIS (Open IIS, Stop and Start the server).

</p>
<br />

![image](https://github.com/user-attachments/assets/7d07bb1a-4d4b-4bab-898c-911e014c72d6)

<p>
Install "osTicket v1.15.8". From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”. Within “c:\inetpub\wwwroot”, Rename the folder “upload” to “osTicket”. Reload IIS (Open IIS, Stop and Start the server). Go to sites -> Default Web Sit -> osTicket, On the right, click “Browse *:80”. If all is done correctly, you must be able to open the osTicket site in your IIS browser.
</p>
<br />


![image](https://github.com/user-attachments/assets/ed647679-bf53-439e-93e4-c73ea4c39859)

<p>
Notice that some extensions are not enabled. Go back to IIS, Sites -> Default Web Site -> osTicket. Double-click PHP Manager. Click “Enable or disable an extension” (Enable: php_imap.dll ,Enable: php_intl.dll, Enable: php_opcache.dll). 

</p>
<br />


![image](https://github.com/user-attachments/assets/28969299-b981-4cc1-b57f-2062e5bfbd89)

<p>
Refresh the osTicket site in your browser, and observe the changes.
</p>
<br />

![image](https://github.com/user-attachments/assets/92471705-bc6a-4dd6-91e2-0eabe22e78db)

<p>
Next rename: "ost-config.php" (From: "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php". To: "C:\inetpub\wwwroot\osTicket\include\ost-config.php"). Assign Permissions: ost-config.php (Disable inheritance -> Remove All inherited permissions, Click add to New Permissions ->type: Everyone -> All). This makes osTicket have full control of the configuration file.

</p>
<br />

![image](https://github.com/user-attachments/assets/97f57258-e6e5-4c00-be07-105bc7ba44de)

<p>
Continue Setting up osTicket in the browser (click Continue). Name Helpdesk (ex: Dilon's Help Desk). Default email (receives email from customers). From the Admin User put you First and Last name, then use a different Email Address compared to Helpdesk. Then use username: adminuser, and password: Password1!
</p>
<br />

![image](https://github.com/user-attachments/assets/e4eb2c70-693b-473f-bf7f-6f113bc27759)

<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL (https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit). Open Heidi SQL. Create a new session, user: root/ pass: root. Connect to the session. Create a database called “osTicket”. To do that, right-click the Unnamed (w/ Dolphin icon), select "Create New" then "Database", name it "osTicket", then hit OK.

</p>
<br />

![image](https://github.com/user-attachments/assets/fe7600c0-f412-42ec-a470-9ab5cef152ee)

<p>
Continue Setting up osTicket in the browser. MySQL Database: osTicket. MySQL Username: root. MySQL Password: root. Click “Install Now!”. 

</p>
<br />

![image](https://github.com/user-attachments/assets/bfef09d6-c5cb-435b-ae73-37253e8a5e1e)

<p>
Congratulations, hopefully it is installed with no errors! Browse to your help desk login page:
http://localhost/osTicket/scp/login.php 
</p>
<br />

![image](https://github.com/user-attachments/assets/013f48ca-3eaa-42f3-a6a7-dd6b30dd382d)

<p>
End Users osTicket URL: "http://localhost/osTicket/". Clean up: Delete: C:\inetpub\wwwroot\osTicket\setup, Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<br />
