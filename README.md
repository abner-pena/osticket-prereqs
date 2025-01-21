<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket<br />



<h2>Environments and Technologies Used</h2>

  - Microsoft Azure (Virtual Machines/Computer)
  - Remote Desktop
  - Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

  - Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

  - Azure Virtual Machine
  - Internet Information Services (IIS)
  - PHP Manager
  - Rewrite Module
  - VC Redist
  - MySQL
  - Heidi SQL
  - osTicket v1.15.8
  - Link to downloads: [Here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)


<h2>Installation Steps</h2>


1. Connect to Your Virtual Machine with Remote Desktop.
    - If you need help connecting to your virtual machine, please see my tutorial [here](https://github.com/abner-pena/virtual-machine)


2. At the bottom left, search for Control Panel
    - Underneath Programs, select Uninstall a Program
    - On the left side of the screen, select Turn Windows Features On or Off
<p>
<img src="https://imgur.com/fGXMpx4.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/LBGkAw6.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3. You will want to install / enable IIS in Windows with CGI and Common HTTP Features
    - World Wide Web Services -> Application Development Features -> 
[X] CGI
[X] Common HTTP Features
  
<p>
<img src="https://imgur.com/LQjw9le.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/pbPeHb1.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***NOTE*** Make sure all Common HTTP Features are checked
 
  - To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 
  It should look something like this 
  
<p>
<img src="https://imgur.com/eICujoq.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
4. Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  Go through the install wizard and complete the install
  
5. Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
  
6. Create a folder in the C drive called PHP
  
7. From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

8. Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe
  
9. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
    - Run the setup wizard:
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

  Make the new root password: Password1
  
<p>
<img src="https://imgur.com/KxcUy7C.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  - Execute the process on the next page
  
<p>
<img src="https://imgur.com/i7sn6hT.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
10.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator
    - The program should look like this
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11. We will now want to register PHP from within IIS
    - Click on PHP Manager
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  - Register new PHP version
  
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  - You will want to provide a path to the php executable file (php-cgi.exe))
  Go to C Drive -> PHP -> click on php-cgi file
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  - Restart the IIS server
  
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12. Install osTicket v1.15.8
    -Download osTicket from the Installation Files Folder
    -Extract and copy "upload" folder to c:\inetpub\wwwroot
    -Within c:\inetpub\root, Rename "upload" to "osTicket"
  
    - Reload IIS again
  
13. On IIS go to sites -> Default -> osTicket
    -On the right, click “Browse *:80”
  
<p>
<img src="https://imgur.com/Yw55d5b.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Some extensions are not enabled on the osTicket browser
  
<p>
<img src="https://imgur.com/eJIsGTn.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- To enable the extensions:
    -Go back to IIS, sites -> Default -> osTicket
    -Double click PHP manager
    -Click "Enable or disable an extension"
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
14. We will want to enable three extensions from here
  
    1.) php_imap.dll
 
    2.) php_intl.dll
  
    3.) php_opcache.dll
  
<p>
<img src="https://imgur.com/cOem7Nb.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
- Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder
-  Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
-  We are going to rename the ost-sampleconfig.php to ost-config.php
-  Now that we have renamed the files, right click on the file and go to properties.
-  From there click security, click on advance, and disable the inheritance
-  We will select Remove all inherited permissions from this object
  
15. Now we will add new permissions
  
-  Click Add
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Select a principal
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
- Type "Everyone" in the box
  
<p>
<img src="https://imgur.com/F4H3ppM.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  Make sure Full Control and all the other boxes are checked
  
<p>
<img src="https://imgur.com/rbbGqwB.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  Click Apply and Ok
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page
-  Fill out the page as required except the Database Settings at the bottom of the page. We will get to that 
-  We will want to download and install HeidiSQL from the Installation Files
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  When the program is open we will create a new session in it
  
<p>
<img src="https://imgur.com/g5M1i61.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  We want to make sure the username is root and the password is Password1
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
-  Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1
  
- We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
16. The next step is to do some clean up. We will want to delete the setup folder in our system
    - Delete: C:\inetpub\wwwroot\osTicket\setup
    - Only delete the setup folder and nothing else
  
-  We then will want to set the permissions back to "Read" only in the ost-config.php file
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 17.  The last step is to login to osTicket on the browser
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Congrats! You have now successfully installed and setup osTicket!
