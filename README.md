<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This guide details the setup requirements and installation steps for the osTicket help desk system, an open-source ticketing solution.<br />

<!--
<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites] / !-->

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (21H2)

<h2>List of Prerequisites</h2>

- PHPManagerForIIS_V.1.5.0.msi
- rewrite_amd64_en-US.msi
- php-7.3.8-nts-Win32-VC15-x86.zip
- VC_redist.x86.exe
- mysql-5.5.62-win32.msi
- osTicket v1.15.8.zip
- HeidiSQL

<b>Link for prerequisites: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6<b/>
<h2>Installation Steps</h2>

<p>
Step 1: In order to begin, you need to create a virtual machine by going to https://portal.azure.com/. Create a virtual machine (VM) with Windows 10 Pro, version 22h2. Your machine needs at least 2vcpus and 16 gbs of memory. Allow the VM to create a new virtual network (Vnet).

<img src="https://i.imgur.com/RUqZkAO.png?1" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 2: After your VM is created, you need to connect to it. Click on your virtual machine and locate the public IP address. You will connect to your machine using Remote Desktop Connection. Copy this address and open up the remote desktop connection. Paste the public IP address and select connect.

<img src="https://i.imgur.com/M9uWjUd.png" title="source: imgur.com" /></a>
<img src="https://i.imgur.com/WiVSjJh.png" title="source: imgur.com" /> </a>
</p>
<br />

<p>
Step 3: Now you need to install/enable IIS on your VM. Right click on the start button, choose run. Inside the run box type: control. Once your control panel opens click on programs, then turn Windows features on or off.

<img src="https://i.imgur.com/qlnaYHd.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 4: Now you will want to enable IIS in windows with CGI and Common HTTP Features. Select Internet Information Services, then select Applictation Development Features, and finally select CGI. Note: Be sure that all Common HTTP features are checked. 

<img src="https://i.imgur.com/XwMktQE.png" title="source: imgur.com" /></a>

To make sure the IIS is installed/enabled properly go to a browser of your choice and search for 127.0.0.1. It should look like the image below.

<img src="https://i.imgur.com/hNYvl4R.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 5: Now that IIS is enabled, from the installation files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi). Go through the install wizard and complete the install.
</p>
<br />

<p>
Step 6: Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en_us.msi).
</p>
<br />

<p>
Step 7: Create a folder in the C drive called PHP.
</p>
<br />

<p>
Step 8: From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP.

!! ATTENTION !! If this appears, choose to "Keep" the file:

<p>
<img src="https://i.imgur.com/AzvI4SW.png" title="source: imgur.com" /></a>

<img src="https://i.imgur.com/z0UH00k.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 9: Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the Installation Files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
</p>
<br />

<p>
Step 10: Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1. Then execute the process on the next page.

<img src="https://i.imgur.com/BhXi5JV.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 11: Now that you have the files downloaded and installed you will want to search for IIS in the windows search bar. Open IIS as an administrator. The program should look like this:   

<p>
<img src="https://i.imgur.com/4qIc0gt.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 12: You will now want to register PHP from within IIS. Clisck on PHP Manager. Register new PHP version. You will want to provide a path to the php executable file (php-cgi.exe)). Go to C drive -> PHP -> click on php-cgi file. 

<p>
<img src="https://i.imgur.com/P0ppTTw.png" title="source: imgur.com" /></a>
</p>

Restart the IIS server.

<p>
<img src="https://i.imgur.com/zkz1dTF.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 13: Install osTicket v1.15.8- Download osTicket from the Installation Files Folder - Extract and copy "upload"folder to c:\inetpub\wwwroot.

<img src="https://i.imgur.com/UcqF6xu.png" title="source: imgur.com" /></a>

Within c:\inetpub\root, Rename "upload" to "osTicket".

<img src="https://i.imgur.com/NIHcmff.png" title="source: imgur.com" /></a>

Reload IIS again. 

<img src="https://i.imgur.com/4qIc0gt.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 14: On IIS go to sites -> Default -> osTicket - On the right, click Browse *.80

<img src="https://i.imgur.com/uiS8eX9.png" title="source: imgur.com" /></a>

Some extensions are not enabled on the osTicket browser.

<img src="https://i.imgur.com/qVhp0nE.png" title="source: imgur.com" /></a>

To enable the extensions: -Go back to IIS, sites -> Default -> osTicket - Double click PHP manager - Click "Enable or disable and extension"  

<img src="https://i.imgur.com/D9HrXVe.png" title="source: imgur.com" /></a>

You will want to enable three extensions from here.

1. php_imap.dll 

2. php_intl.dll

3. php_opcache.dll

<img src="https://i.imgur.com/G7Qe7bh.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 15: Once you have those extensions enabled in IIS, you are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

You are going to rename the ost-sampleconfig.php to ost-config.php

Now that you have renamed the files, right click on the file and go to properties. From there click security, click on advanced, and disable the inheritance. You will select Remove all inherited permissions from this object.

<img src="https://i.imgur.com/iIEZVEa.png" title="source: imgur.com" /> </a>
</p>
<br />

<p>
Step 16: Now you will add new permissions.

Click Add.

<img src="https://i.imgur.com/HkPzNXq.png" title="source: imgur.com" /></a>

Select a principal.

<img src="https://i.imgur.com/AUQUKOf.png" title="source: imgur.com" /></a>

Type "Everyone" in the box.

<img src="https://i.imgur.com/Z01ydUQ.png" title="source: imgur.com" /></a>

Make sure Full Control and all the other boxes are checked.

<img src="https://i.imgur.com/QnbdnW8.png" title="source: imgur.com" /></a>

Click Apply and OK.

<img src="https://i.imgur.com/NLL8MZQ.png" title="source: imgur.com" /></a>
</p>
<br />

<p>
Step 17: Once the previous step is completed, you will continue to setup osTicket in the browser. Click continue on the osTicket broweser page. Fill out the page as required EXCEPT the Database Settings at the bottom of the page. You will get to that in a moment.

<img src="https://i.imgur.com/EHiOArh.png" title="source: imgur.com" /></a>

You will want to download and install HeidiSQL from the installation files.

<img src="https://i.imgur.com/gq0oaYN.png" title="source: imgur.com" /></a>

When the program is open you will create a new sesssion in it.

<img src="https://i.imgur.com/8AXBExy.png" title="source: imgur.com" /></a>

In Heidi, make sure the username is root and the password is Password1.

<img src="https://i.imgur.com/WbMEe6Z.png" title="source: imgur.com" /></a>

Once you are connected to the session, you will go back to the browser to finish setting everything up. Under the Database settings in the browswer, the username will be root and the password will be Password1.

<img src="https://i.imgur.com/7TSwh8Z.png" title="source: imgur.com" /></a>
</p>
</br>

<p>
Step 18: You will now create a new database withing HeidiSQL. In Heidi right click on the left side where it says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup, go backt to the osTiceket browser and under MySQL Database type in osTicket.

<img src="https://i.imgur.com/wzqvvfa.png" title="source: imgur.com" /></a>
</p>
</br>

Step 19: The last step is to do some clean up. You will want to delete the setup folder in our system. - Delete: C:\inetpub\wwwroot\osTicket\setup. Be sure to delete only this folder.

You will then want to set the permissions back to "read only" in the ost-config.php file.

<img src="https://i.imgur.com/vyJVef9.png" title="source: imgur.com" /></a>

<img src="https://i.imgur.com/p7G0LBS.png" title="source: imgur.com" /></a>

The last step after that is to login to osTicket on the browser.

<img src="https://i.imgur.com/gpxSXxw.png" title="source: imgur.com" /></a>
</p>
<br />

Congrats! You have now successfully installed and setup osTicket!












