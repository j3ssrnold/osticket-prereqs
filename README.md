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
</p>
<p>
<img src="https://images2.imgbox.com/4e/26/fj4RKSC5_o.png" alt="image host"/></a>
</p>
<br />

<p>
Step 2: After your VM is created, you need to connect to it. Click on your virtual machine and locate the public IP address. You will connect to your machine using Remote Desktop Connection. Copy this address and open up the remote desktop connection. Paste the public IP address and select connect.
</p>
<p>
<img src="https://images2.imgbox.com/1f/4c/cWFvMGCp_o.png" alt="imgbox"/>
<img src="https://images2.imgbox.com/26/af/Gboy1qGC_o.png" alt="imgbox"/></a> 
</p>
<br />

<p>
Step 3: Now you need to install/enable IIS on your VM. Right click on the start button, choose run. Inside the run box type: control. Once your control panel opens click on programs, then turn Windows features on or pff.
</p>
<p>
<img src="https://images2.imgbox.com/ea/26/EheoO4J8_o.png" alt="image host"/></a>
</p>
<br />

<p>
Step 4: Now you will want to enable IIS in windows with CGI and Common HTTP Features. Select Internet Information Services, then select Applictation Development Features, and finally select CGI. Note: Be sure that all Common HTTP features are checked. 
</p>
<p>
<img src="https://images2.imgbox.com/99/e3/hAvfqiKq_o.png" alt="imgbox"/></p>
</p>
<br />

<p>
To make sure the IIS is installed/enabled properly go to a browser of your choice and search for 127.0.0.1. It should look like the image below.
</p>
<p>
<img src="https://images2.imgbox.com/c4/96/6MUzGjdr_o.png" alt="imgbox"/></a>
</p>
</br>

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

<p>
Step 8: From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP.
</p>

<p>
!! ATTENTION !! If this appears, choste to "Keep" the file:
<p>
<img src="https://images2.imgbox.com/f8/74/tebKMH05_o.png" alt="imgbox"/>

  <img src="https://images2.imgbox.com/0c/1b/ITIVZg9C_o.png" alt="imgbox"/></a>
</p>

<p>
Step 9: Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the Installation Files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
</p>
<br />

<p>
Step 10: Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->
</p>
<p>
Make the new root password: Password1. Then execute the process on the next page.
</p>
<p>
<img src="https://images2.imgbox.com/dc/aa/xn3ECy4c_o.png" alt="imgbox"/></a>
</p>
</br>

<p>
Step 11: Now that you have the files downloaded and installed you will want to search for IIS in the windows search bar. Open IIS as an administrator. The program should look like this:   
</p>
<p>
<img src="https://images2.imgbox.com/8f/e0/4dfWHPQ2_o.png" alt="imgbox"/></a>
</p>
</br>

<p>
Step 12: You will now want to register PHP from within IIS. Clisck on PHP Manager. Register new PHP version. You will want to provide a path to the php executable file (php-cgi.exe)). Go to C drive -> PHP -> click on php-cgi file. 
</p>
<p>
<img src="https://images2.imgbox.com/e0/96/Jpuv6tiI_o.png" alt="imgbox"/></a>
</p>
<p>
Restart the IIS server.
</p>
<p>
<img src="https://images2.imgbox.com/b1/66/INzy2Cnq_o.png" alt="image host"/></a>
</p>
</br>

<p>
Step 13: Install osTicket v1.15.8- Download osTicket from the Installation Files Folder - Extract and copy "upload"folder to c:\inetpub\wwwroot.
</p>
<p>
<img src="https://images2.imgbox.com/ed/03/e3vXUEsB_o.png" alt="imgbox"/>

Within c:\inetpub\root, Rename "upload" to "osTicket".

<img src="https://images2.imgbox.com/a0/bb/1dgTSnkQ_o.png" alt="imgbox"/></a>
</p>
<p>
Reload IIS again. 
</p>
</br>

<p>
Step 14: On IIS go to sites -> Default -> osTicket - On the right, click Browse *.80
</p>
<p>
<img src="https://images2.imgbox.com/70/a3/UvWrMoqd_o.png" alt="image host"/></a>
</p>
<p>
Some extensions are not enabled on the osTicket browser.
</p>
<p>
<img src="https://images2.imgbox.com/dd/6f/LQASJdAN_o.png" alt="image host"/></a>
</p>
<p>
To enable the extensions: -Go back to IIS, sites -> Default -> osTicket - Double click PHP manager - Click "Enable or disable and extension"  
</p>
<p>
<img src="https://images2.imgbox.com/5a/7d/UdUXcy81_o.png" alt="image host"/></a>
</p>
<p>
You will want to enable three extensions from here.
</p>
<p>
1. php_imap.dll 
</p>
<p>
2. php_intl.dll
</p>
<p>
3. php_opcache.dll
</p>
<p>
<img src="https://images2.imgbox.com/8b/26/6AZXXgPs_o.png" alt="image host"/></a>
</p>
</br>

<p>
Step 15: Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

You are going to rename the ost-sampleconfig.php to ost-config.php

Now that you have renamed the files, right click on the file and go to properties. From there click security, click on advanced, and disable the inheritance. You will select Remove all inherited permissions from this object.

<p>
<img src="https://images2.imgbox.com/ad/87/wTtdbGXV_o.png" alt="image host"/></a> 
</p>

Now we will add new permissions.

Click Add.

<p>
<img src="https://images2.imgbox.com/f9/4e/Y9zeUl4T_o.png" alt="image host"/></a>
</p>

Select a principal.

<p>
<img src="https://images2.imgbox.com/67/61/FXgB5SpG_o.png" alt="image host"/></a>  
</p>

Type "Everyone" in the box.

<p>
<img src="https://images2.imgbox.com/f8/22/NQxhS6Qn_o.png" alt="image host"/></a>
</p>

Make sure Full Control and all the other boxes are checked.

<p>
<img src="https://images2.imgbox.com/93/65/GuY8UEw7_o.png" alt="image host"/></a>  
</p>

Click Apply and OK.

<p>
<img src="https://images2.imgbox.com/e7/8e/VQNf3VyP_o.png" alt="image host"/></a>
</p>
</br>

<p>
Step 16: Once the previous step is completed, you will continue to setup osTicket in the browser. Click continue on the osTicket broweser page. Fill out the page as required EXCEPT the Database Settings at the bottom of the page. You will get to that in a moment.

<p>
<img src="https://images2.imgbox.com/d8/34/rxnfMMrL_o.png" alt="imgbox"/></a> 
</p>
</br>

<p>
You will want to download and install HeidiSQL from the installation files.

<p>
<img src="https://images2.imgbox.com/00/7e/2akb7H36_o.png" alt="image host"/></a>
</p>  

When the program is open you will create a new sesssion in it.

<p>
<img src="https://images2.imgbox.com/2d/f7/cXNiaTiC_o.png" alt="image host"/></a>
</p>

You want to make sure the username is root and the password is Password1.

<p>
<img src="https://images2.imgbox.com/12/c7/zSNlMCto_o.png" alt="imgbox"/></a>
</p>

Once you are connected to the session, you will go back to the browser to finish setting everything up. Under the Database settings in the browswer, the username will be root and the password will be Password1.

<p>
Step 17: You will now create a new database withing HeidiSQL. In Heidi right click on the left side where it says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup, go backt to the osTiceket browser and under MySQL Database type in osTicket.

<p>
<img src="https://images2.imgbox.com/c3/a4/4UO98WMO_o.png" alt="image host"/></a>
</p>
</br>

<p>
Step 18: The last step is to do some clean up. You will want to delete the setup folder in our system. - Delete: C:\inetpub\wwwroot\osTicket\setup. Be sure to delete only this folder.

You will then want to set the permissions back to "read only" in the ost-config.php file.

<p>
<img src="https://images2.imgbox.com/2a/25/vOhmbPOP_o.png" alt="image host"/>

<img src="https://images2.imgbox.com/f6/ca/TeDEQky4_o.png" alt="image host"/></a>
</p>

The last step after that is to login to osTicket on the browser.

<p>
<img src="https://images2.imgbox.com/c4/f1/iG5Xsya0_o.png" alt="imgbox"/></a>
</p>

Congrats! You have now successfully installed and setup osTicket!












