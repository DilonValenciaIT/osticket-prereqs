<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
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
Welcome to this step-by-step IT tutorial. To begin, an Azure Virtual Machine with a Windows 10 operating system and 4 vCPUs should be created. This VM will be named 'osticket-vm.' A username, 'labuser,' and a password, 'osTicketPassword1!,' should be used. The VM should be placed in the 'osTicket' Resource Group. Using the provided credentials, log into the VM via Remote Desktop Connection using its public IPv4 address. Within the VM ('osticket-vm'), download the 'osTicket-Installation-Files.zip' file (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract it to the desktop. The extracted folder should be named 'osTicket-Installation-Files.' The files within this folder will be used to install osTicket and its dependencies
</p>
<br />

![image](https://github.com/user-attachments/assets/23d21404-8641-45af-92f8-8461eb400846)

<p>
Now that the connection to the VM has been established, IIS (Internet Information Services) with CGI must be installed and enabled in Windows. To do this, navigate to the Control Panel, then select 'Uninstall Programs.' On the left-hand side, click 'Turn Windows features on or off.' A list of features will appear—select 'Internet Information Services,' then expand it to reveal 'World Wide Web Services.' Expand 'Application Development Features' and select 'CGI,' then click 'OK.' This will install the Web Server, ensuring that IIS (127.0.0.1) is operational.

From the 'osTicket-Installation-Files' folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi). Next, install the Rewrite Module (rewrite_amd64_en-US.msi) from the same folder. Create a new directory at 'C:\PHP.' Then, extract PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the 'osTicket-Installation-Files' folder into the 'C:\PHP' directory. Additionally, install 'VC_redist.x86.exe' from the same folder.

Next, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the 'osTicket-Installation-Files' folder. Use the 'Typical Setup' option, then proceed with the 'Launch Configuration Wizard' after installation. Choose 'Standard Configuration' and set the username to 'root' and the password to 'root.'

Open IIS as an administrator. Register PHP within IIS by navigating to 'PHP Manager' and selecting 'Register new PHP version,' then specifying the path 'C:\PHP\php-cgi.exe.' Finally, reload IIS by opening the IIS Manager and stopping and restarting the server.

</p>
<br />

![image](https://github.com/user-attachments/assets/7d07bb1a-4d4b-4bab-898c-911e014c72d6)

<p>
Install 'osTicket v1.15.8.' From the 'osTicket-Installation-Files' folder, extract 'osTicket-v1.15.8.zip' and copy the 'upload' folder into 'C:\inetpub\wwwroot.' Within 'C:\inetpub\wwwroot,' rename the 'upload' folder to 'osTicket.'

Reload IIS by opening IIS Manager and stopping and restarting the server. Navigate to 'Sites' -> 'Default Web Site' -> 'osTicket.' On the right-hand side, click 'Browse *:80.' If all steps have been completed correctly, the osTicket site should open in the IIS browser.
</p>
<br />


![image](https://github.com/user-attachments/assets/ed647679-bf53-439e-93e4-c73ea4c39859)

<p>
Some extensions may not be enabled. To resolve this, return to IIS and navigate to 'Sites' -> 'Default Web Site' -> 'osTicket.' Double-click 'PHP Manager,' then select 'Enable or disable an extension.' Enable the following extensions: 'php_imap.dll,' 'php_intl.dll,' and 'php_opcache.dll.

</p>
<br />


![image](https://github.com/user-attachments/assets/28969299-b981-4cc1-b57f-2062e5bfbd89)

<p>
Refresh the osTicket site in the browser and observe the changes.
</p>
<br />

![image](https://github.com/user-attachments/assets/92471705-bc6a-4dd6-91e2-0eabe22e78db)

<p>
Next, rename the file 'ost-sampleconfig.php' located in 'C:\inetpub\wwwroot\osTicket\include' to 'ost-config.php.'

Then, assign the necessary permissions to 'ost-config.php.' Disable inheritance and remove all inherited permissions. Click 'Add' to create new permissions, then enter 'Everyone' and grant full control. This ensures that osTicket has full control over the configuration file.

</p>
<br />

![image](https://github.com/user-attachments/assets/97f57258-e6e5-4c00-be07-105bc7ba44de)

<p>
Continue setting up osTicket in the browser by clicking 'Continue.' Enter a name for the Helpdesk (e.g., 'Dilon's Help Desk'). Specify the default email address, which will receive emails from customers.

In the Admin User section, enter the first and last name of the administrator. Use an email address different from the Helpdesk email. Set the username as 'adminuser' and the password as 'Password1!
</p>
<br />

![image](https://github.com/user-attachments/assets/e4eb2c70-693b-473f-bf7f-6f113bc27759)

<p>
From the 'osTicket-Installation-Files' folder, install HeidiSQL (https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit).

Open HeidiSQL and create a new session using the username 'root' and password 'root.' Connect to the session.

Next, create a database named 'osTicket.' To do this, right-click the 'Unnamed' session (with the Dolphin icon), select 'Create New,' then choose 'Database.' Name the database 'osTicket' and click 'OK.

</p>
<br />

![image](https://github.com/user-attachments/assets/fe7600c0-f412-42ec-a470-9ab5cef152ee)

<p>
Continue setting up osTicket in the browser. For the MySQL Database, enter 'osTicket.' For the MySQL Username, use 'root,' and for the MySQL Password, enter 'root.' Then, click 'Install Now!'
</p>
<br />

![image](https://github.com/user-attachments/assets/bfef09d6-c5cb-435b-ae73-37253e8a5e1e)

<p>
Congratulations! The installation should be complete without any errors. To access the help desk login page, browse to:
http://localhost/osTicket/scp/login.php
</p>
<br />

![image](https://github.com/user-attachments/assets/013f48ca-3eaa-42f3-a6a7-dd6b30dd382d)

<p>
End Users can access osTicket via the following URL: 'http://localhost/osTicket/'.

For cleanup, delete the 'C:\inetpub\wwwroot\osTicket\setup' folder. Then, set the permissions for 'C:\inetpub\wwwroot\osTicket\include\ost-config.php' to 'Read' only.
</p>
<br />
