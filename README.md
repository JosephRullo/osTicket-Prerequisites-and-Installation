<p align="center">
<img src="https://imgur.com/C9d2T2j.png" height="100%" width="100%" alt="Disk Sanitization Steps alt="osTicket logo"/>
</p>
<h1> <p align="center"> osTicket - Prerequisites and Installation</h1> 
<p align="center">
<p align="center"> This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.
<br />
<br />
<br /> 
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure account 
- PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Rewrite Module (rewrite_amd64_en-US.msi) 
- PHP 7.3.8 
- VC_redist.x86.exe
- MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- osTicket v1.15.8
- HeidiSQL


<h2>Installation Steps</h2>


<h2>Step 1.</h2> 

**Create Azure Virtual Machine** 
<p>
This entire installation will be performed on a Virtual Machine created in Microsoft's Azure cloud computing platform. For a tutorial on setting up Virtual Machines in Azure click this link:
<p>
https://github.com/JosephRullo/Azure-Virtual-Machines-and-Networking/blob/main/README.md). 
<p> 
Let's begin with creating one running Window's 10 with 2-4 Virtual CPU's. Note, this step can be skipped if you are installing it on a PC at your work location.
<p>
<p>
<img src="https://i.imgur.com/U1HVP9X.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 2.</h2> 

**Install / Enable IIS in Windows with CGI and Common HTTP Features.** 
<p>
To do this open the control panel, select Programs and then click "Turn Windows features on or off". From here expand the folder labeled Internet Information Services -> Web Management Tools and check the box for IIS Management Console. Do the same for the folder labeled Internet Information Services -> World Wide Web Services -> Application Development Features and check the box for CGI, as well as checking the Common HTTP Features folder.
<p>
<img src="https://i.imgur.com/DIujP9h.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/K33PxLk.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/k6QTnHW.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wotvBv2.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 3.</h2> 

**Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)**
<p>
(https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10)
<p>
<p>
<img src="https://imgur.com/WxftCi4.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 4.</h2> 

**Download and install Rewrite Module (rewrite_amd64_en-US.msi)**
<p>
(https://www.iis.net/downloads/microsoft/url-rewrite)
<p>
<p>
<img src="https://imgur.com/3JxWkZg.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
 </p>
<br />

<h2>Step 5.</h2>  

**Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip).** 
<p>
(https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link)
<p>
Next create the directory C:\PHP. To do this go to the C:\ drive and create a new folder in it named PHP. Now download PHP 7.3.8 -> Unzip and Extract the contents of it into C:\PHP.
<p>
<p>
<img src="https://i.imgur.com/M1y1IYe.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
<br />

<h2>Step 6.</h2>  

**Download and install VC_redist.x86.exe (Microsoft Visual C ++)**
<p>
(https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170)
<p>
<p>
<img src="https://imgur.com/55Z0SVc.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 7.</h2> 

**Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi).**
<p>
(https://dev.mysql.com/downloads/mysql/5.5.html)
<p> 
Now let's configure MySQL, a popular open source database. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Select Typical Setup when prompted and check the box for Launch Configuration Wizard (after install). Choose Standard Configuration -> Install as Windows Service -> choose a password and finish the install.
<p>
<p>
<img src="https://imgur.com/9CGk2QI.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/o6j4UuT.png" height="50%" width="50%" alt="Disk Sanitization Steps"/> 
<img src="https://imgur.com/VGilvlV.png" height="50%" width="50%" alt="Disk Sanitization Steps"/> 
<img src="https://imgur.com/vNEISe8.png" height="50%" width="50%" alt="Disk Sanitization Steps"/> 
<img src="https://imgur.com/84OcpT4.png" height="50%" width="50%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 8.</h2>  

**Open Internet Information Services (IIS) as an Admin**
<p>
Go to the start menu and type IIS, right click on it and select Run as Administrator.
<p>
<p>
<img src="https://i.imgur.com/FNhVUTm.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 9.</h2> 

**Register PHP Manager**
<p>
Select PHP Manager from within IIS and click on Register new PHP version. In the Register new PHP window, select the CGI file that we installed in step 2. Now restart the IIS server by clicking on Restart in the upper right hand corner of the IIS window (as shown in the screenshot below).
<p>
<p>
<img src="https://i.imgur.com/Zp0OtuD.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/LueRyMH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/arILgVt.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
<img src="https://imgur.com/0oXHWnI.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/8GtfKZz.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 10.</h2>

**Install osTicket**
<p>
(https://osticket.com/download/)
<p> 
Now it's time to install osTicket. First download osTicket v1.15.8. Once downloaded copy the folder inside of it labeled "upload" and paste it in this directory c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”. Go back to the IIS window and restart the IIS server again by clicking the Restart button in the upper right corner.
<p>
<p>
<img src="https://i.imgur.com/dELqHg5.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/bShIQez.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/8GtfKZz.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 11.</h2> 

**Open osTicket Install Window**
<p>
We can now open the osTicket install window by going to the IIS -> selecting the drop down folder under Connections (on the left side of the window) -> go to sites -> Default -> osTicket. Now click on “Browse *:80” under the browse folder all the way on the right. This will open a new web browser window with the osTicket installer menu.
<p>
<p>
<img src="https://i.imgur.com/SCxVMYE.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
<img src="https://imgur.com/31tJJAG.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 12.</h2> 

**Enable Extensions for the osTicket Installer**
<p>
Note that some extensions are not enabled in the installer screen above. Go back to IIS, sites -> Default -> osTicket. Now double-click PHP Manager -> Click “Enable or disable an extension” and enable the following extensions: 
<p> 
 
**php_imap.dll**
<p>
 
**php_intl.dll**
<p>
 
**php_opcache.dll**
<p>
<p>
<img src="https://i.imgur.com/fbIGV86.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2>Step 13.</h2> 

**Refresh the osTicket Site in your Browser**
<p>
observe the changes in the enabled extensions.
<p>
<p>
<img src="https://i.imgur.com/PswXdwH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 14.</h2> 

**Rename ost-sampleconfig.php.**
<p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php change this to: C:\inetpub\wwwroot\osTicket\include\ost-config.php
<p>
<p>
<img src="https://i.imgur.com/lEURFNX.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 15.</h2> 

**Assign Permissions: ost-config.php.**
<p>
Right click on C:\inetpub\wwwroot\osTicket\include\ost-config.php and select Properties. Go to the Security tab and choose Advanced. In the Advanced tab click on Disable inheritance and select Remove All Permissions.
<p>
<p>
<p>
<img src="https://i.imgur.com/orbsGci.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 16.</h2> 

**Assign Permissions (continued):**
<p>
Right click on C:\inetpub\wwwroot\osTicket\include\ost-config.php and select Properties. Go to the Security tab and choose Edit. In the Edit tab set Principal to Everyone -> Type: Allow -> Check all permission boxes -> click OK.
<p>
<p>
<p>
<img src="https://i.imgur.com/RzqzHAg.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 17.</h2>  

**Download and install HeidiSQL**
<p>
(https://www.heidisql.com/download.php)
<p>
This will allow us to connect to the MySQL sever and setup a database that osTicket will use. After downloading and installing, Open Heidi SQL -> Click "New" on the bottom left corner to create a new session -> For the username type "root" and enter the same password used for MySQL that was created in step 7 -> Click "Open". Now we will create a new database named osTicket. To do this right click on the "Unamed" tab on the left hand side of the HeidiSQL window and select "Create new" -> select "Database" -> name it "osTicket" -> click ok.
<p>
<p>
<p>
<img src="https://imgur.com/Wh0nI0L.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/pwJPBSs.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/G2r6Wxw.png"height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 18.</h2> 

**Continue Setting up osTicket in the browser (click Continue).**
<p>
<p>
<p>
<img src="https://i.imgur.com/IvyhYmS.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 19.</h2> 

**Fill out the information required for System Settings/Admin User/Database Settings.**
<p>
For the "System Settings" section enter a unique "Helpdesk Name" and "Default Email" of your choice (for this example I am simply using Helpdesk for the name and helpdesk@osTicket.com for the email.) For the "Admin User" section fill in the name of who will be assigned this role along with their email. Now assign their "Username" and "Password" for logging in (make sure to save this information somewhere secure). In the "Database Settings" section enter in the the "MySQL Database" field the database name we just created in HeidiSQL called "osTicket". For the the "MySQL Username" enter "root" and for the "MySQL Password" enter in the password you assigned in the previous steps. Finally click "Install Now".
<p>
<p>
<p>
<img src="https://i.imgur.com/bpctQAF.png" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
<p>
</p>
<br />

<h2>Step 20.</h2> 

**Congratulations**
<p>
osTicket setup is now complete! You can log in as the administrator using the following link: http://localhost/osTicket/scp/login.php
<p>
<p>
<p>
<img src="https://i.imgur.com/wMHKJHT.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/gprXh5g.jpg" height="60%" width="60%" alt="Disk Sanitization Steps"/> 
</p>
</p>
<p>
</p>
<br />

<h2>Step 21.</h2> 

**Install Cleanup.**
<p>
Delete the "setup" folder located here C:\inetpub\wwwroot\osTicket. Finally set Permissions to “Read” only for the ost-config.php file located here: C:\inetpub\wwwroot\osTicket\include\ost-config.php. 
<p>
<p>
<p>
<img src="https://i.imgur.com/vIfMsT2.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>  
<img src="https://i.imgur.com/4KzTyTC.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

<h2> <p align="center"> This Concludes the osTicket Installation Tutorial. Good Job!!!</h2>
