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


<h3>Step 1: In order to begin, you must first create a Virtual Machine (VM). Create a virtual machine (VM) with Windows 10 Pro, version 22h2. Your machine needs at least 2vcpus and 16 gbs of memory. Allow the VM to create a new virtual network (Vnet).</h3>

-  Go to the [Azure Portal](https://portal.azure.com) --> Search for Virtual Machines --> Create VM with Windows 10 Pro, version 22h2 --> Click next ***twice*** --> Allow the portal to create a new virtual network (Vnet). --> Review and Create.

    <p>
    <img src="https://i.imgur.com/RUqZkAO.png?1" title="source: imgur.com" /></a>
    </p>

>[!NOTE]
>Your VM needs at least 2vcpus and 16 gbs of memory to run effieciently.
<br />

<h3>Step 2: Connect to your VM using Remote Desktop Connection.</h3>

-  Click VM --> Copy the public IP address -->  Open Remote Desktop Connection --> Paste the public IP --> Select Connect.

    <p>
    <img src="https://i.imgur.com/M9uWjUd.png" title="source: imgur.com" /></a>
    <img src="https://i.imgur.com/WiVSjJh.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 3: Install and enable IIS on your VM. </h3>

-  Right click start button --> Choose Run --> Type **control** inside run box --> Control Panel --> Click Programs --> Turn Windows features on or off.

    <p>
    <img src="https://i.imgur.com/qlnaYHd.png" title="source: imgur.com" /></a>
    </p>


-  Now you will want to enable IIS in windows with CGI and Common HTTP Features.
    -  Select Internet Information Services --> --> Applictation Development Features --> CGI.  

    <p>
    <img src="https://i.imgur.com/XwMktQE.png" title="source: imgur.com" /></a>
    </p>

>[!IMPORTANT]
>Be sure that **ALL** Common HTTP Features are checked.
<br />

-  Make sure IIS is installed/enabled properly.
    -  Go to browser of your choice --> Search for 127.0.0.1 --> It should look like the image below:

    <p>
    <img src="https://i.imgur.com/hNYvl4R.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 4: From the installation files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi).</h3> 

-  Go through the install wizard and complete the install.

<h3>Step 5: Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en_us.msi).</h3>

-  Complete the install wizard.

<h3>Step 6: Create a folder in the C drive called PHP.</h3>

<h3>Step 7: From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP.</h3>
    <p>
    <img src="https://i.imgur.com/AzvI4SW.png" title="source: imgur.com" /></a>
    <img src="https://i.imgur.com/z0UH00k.png" title="source: imgur.com" /></a>
    </p>

>[!WARNING]
>If this appears, choose to **KEEP** the file. If you continue having trouble downloading PHP 7.3.8, try to downloading and installing [Google Chrome](https://google.com/chrome/) and trying from there.
<br />

<h3>Step 8: Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the Installation Files.</h3>

-  Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.</b>

<h3>Step 9: Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi).</h3> 

 -  Run Setup wizard -->Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration
    -  Make the new root password: Password1 --> Execute the process on the next page.

    <p>     
    <img src="https://i.imgur.com/BhXi5JV.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 10: Open IIS as an administrator.</h3> 

-  Windows Search Bar --> IIS --> Right Click IIS --> Select Run as Administrator --> The program should look like this:

    <p>
    <img src="https://i.imgur.com/4qIc0gt.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 11: Register PHP from within IIS.</h3>

-  Click on PHP Manager --> Register new PHP version --> Provide a path to the php executable file (php-cgi.exe). Go to C drive -> PHP -> click on php-cgi file.

    <p>
    <img src="https://i.imgur.com/P0ppTTw.png" title="source: imgur.com" /></a>
    </p>
<br />

- Restart the IIS server.

    <p>
    <img src="https://i.imgur.com/zkz1dTF.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 12: Install osTicket v1.15.8.</h3> 

-  Download osTicket from the Installation Files Folder --> Extract and copy "upload" folder to c:\inetpub\wwwroot.

    <p>
    <img src="https://i.imgur.com/UcqF6xu.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Within c:\inetpub\root, Rename "upload" to "osTicket".

    <p>
    <img src="https://i.imgur.com/NIHcmff.png" title="source: imgur.com" /></a>
    </p>
<br />

- Reload IIS again. 

    <p>
    <img src="https://i.imgur.com/4qIc0gt.png" title="source: imgur.com" /></a>
    </p>
<br />

<H3>Step 13: Navigate to the osTicket Installer.</h3>

-   On IIS go to sites -> Default -> osTicket - On the right, click Browse *.80

    <p>
    <img src="https://i.imgur.com/uiS8eX9.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Some extensions are not enabled on the osTicket browser.

    <p>
    <img src="https://i.imgur.com/qVhp0nE.png" title="source: imgur.com" /></a>
    </p>
<br />

-  To enable the extensions: Go back to IIS, sites -> Default -> osTicket - Double click PHP manager - Click "Enable or disable and extension"  

    <p>
    <img src="https://i.imgur.com/D9HrXVe.png" title="source: imgur.com" /></a>
    </p>
<br />

-  You will want to enable three extensions from here.

  - 1. php_imap.dll


  - 2. php_intl.dll


  - 3. php_opcache.dll

    <p>
    <img src="https://i.imgur.com/G7Qe7bh.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 14: Once you have those extensions enabled in IIS, rename one of the files in your osTicket folder.</h3> 

-  Go into the file explorer and search for C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</b>
    -  You are going to rename the ost-sampleconfig.php to ost-config.php
      -  Now that you have renamed the files, right click on the file and go to properties. From there click security, click on advanced, and disable the inheritance. You will select Remove all inherited permissions from this object.

    <p>
    <img src="https://i.imgur.com/iIEZVEa.png" title="source: imgur.com" /> </a>
    </p>
<br />

<h3>Step 15: Now you will add new permissions.</h3>

-  Click Add.

    <p>
    <img src="https://i.imgur.com/HkPzNXq.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Select a principal.

    <p>
    <img src="https://i.imgur.com/AUQUKOf.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Type "Everyone" in the box.

    <p>
    <img src="https://i.imgur.com/Z01ydUQ.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Make sure Full Control and all the other boxes are checked.

    <p>
    <img src="https://i.imgur.com/QnbdnW8.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Click Apply and OK.

    <p>
    <img src="https://i.imgur.com/NLL8MZQ.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 16: Once the previous step is completed, you will continue to setup osTicket in the browser.</h3>

-  Click continue on the osTicket broweser page. -- > Fill out the page EXCEPT the Database Settings at the bottom of the page. You will get to that in a moment.

    <p>
    <img src="https://i.imgur.com/EHiOArh.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Step 17: Install HeidiSQL from the installation files.</h3>

-  Be sure that Launch HeidiSQL is checked.

    <p>
    <img src="https://i.imgur.com/gq0oaYN.png" title="source: imgur.com" /></a>
    </p>
<br />

-  When the program is open you will create a new sesssion in it.

    <p>
    <img src="https://i.imgur.com/8AXBExy.png" title="source: imgur.com" /></a>
    </p>
<br />

-  In Heidi, make sure the username is root and the password is Password1.

    <p>
    <img src="https://i.imgur.com/WbMEe6Z.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Connect to the session --> go back to the browser to finish setting up. --> Under the Database settings, the username will be root and the password will be Password1.

    <p>
    <img src="https://i.imgur.com/7TSwh8Z.png" title="source: imgur.com" /></a>
    </p>
</br>

<h3>Step 18: You will now create a new database withing HeidiSQL.</h3>

-  Heidi --> right click on the left side where it says "Unnamed" --> Select "create new" --> Select "database" --> Name the new database osTicket.
  -  Once we have the new database setup, go backt to the osTicket browser and under MySQL Database type in osTicket.</b>
    <p>
    <img src="https://i.imgur.com/wzqvvfa.png" title="source: imgur.com" /></a>
    </p>
</br>

<h3>Step 19: Do some clean up.</h3> 

-  You will want to delete the setup folder in our system. - Delete: C:\inetpub\wwwroot\osTicket\setup. Be sure to delete only this folder.</b>
 
    <p>
    <img src="https://i.imgur.com/vyJVef9.png" title="source: imgur.com" /></a>
    </p>
<br />

-  You will then want to set the permissions back to "read only" in the ost-config.php file.

    <p>
    <img src="https://i.imgur.com/p7G0LBS.png" title="source: imgur.com" /></a>
    </p>
<br />

-  Finally, the last step is to login to osTicket on the browser.

    <p>
    <img src="https://i.imgur.com/gpxSXxw.png" title="source: imgur.com" /></a>
    </p>
<br />

<h3>Congrats! You have now successfully installed and setup osTicket!</h3>

<br />









