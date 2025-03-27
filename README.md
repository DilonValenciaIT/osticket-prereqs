<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5


<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/df81e24f-e702-46f0-a5de-f906c70d4fbb)

<p>
To get started, we must create an Azure Virtual Machine with a Windows 10 operating system and 4 vCPUS. Let us name this VM the "osticket-vm", with a username called "labuser" and a password called "osTicketPssword1!". With the username and password we will now be logging into the VM with Remote Desktop Connection. Within the VM (osticket-vm), download osTicket-Installation-Files.zip (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it into the desktop. The folder should be called “osTicket-Installation-Files”. We will use the files in this folder to install osTicket and some of the dependencies.
</p>
<br />

![image](https://github.com/user-attachments/assets/23d21404-8641-45af-92f8-8461eb400846)

<p>
Up next, install and enable IIS in Windows with CGI (World Wide Web Services > Application Development Features > [X] CGI). From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi). From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi). Create the directory "C:\PHP". 
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder. From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe. From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Typical Setup ->Launch Configuration Wizard (after install) ->Standard Configuration ->Username: root Password: root. Open IIS as an Admin. Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe). Reload IIS (Open IIS, Stop and Start the server).

</p>
<br />

![image](https://github.com/user-attachments/assets/7d07bb1a-4d4b-4bab-898c-911e014c72d6)

<p>
Install "osTicket v1.15.8". From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”. Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”. Reload IIS (Open IIS, Stop and Start the server). Go to sites -> Default -> osTicket, On the right, click “Browse *:80”. 
</p>
<br />


![image](https://github.com/user-attachments/assets/ed647679-bf53-439e-93e4-c73ea4c39859)

<p>
Note that some extensions are not enabled. Go back to IIS, sites -> Default -> osTicket. Double-click PHP Manager. Click “Enable or disable an extension” (Enable: php_imap.dll ,Enable: php_intl.dll, Enable: php_opcache.dll). Refresh the osTicket site in your browser, observe the changes.

</p>
<br />


![image](https://github.com/user-attachments/assets/28969299-b981-4cc1-b57f-2062e5bfbd89)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/92471705-bc6a-4dd6-91e2-0eabe22e78db)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/97f57258-e6e5-4c00-be07-105bc7ba44de)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/e4eb2c70-693b-473f-bf7f-6f113bc27759)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/fe7600c0-f412-42ec-a470-9ab5cef152ee)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/bfef09d6-c5cb-435b-ae73-37253e8a5e1e)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/013f48ca-3eaa-42f3-a6a7-dd6b30dd382d)

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
