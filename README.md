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
<img src="https://images2.imgbox.com/4e/26/fj4RKSC5_o.png" alt="image host"/></a>
</p>
Step 1: In order to begin, you need to create a virtual machine by going to https://portal.azure.com/. Create a virtual machine (VM) with Windows 10 Pro, version 22h2. Your machine needs at least 2vcpus and 16 gbs of memory. Allow the VM to create a new virtual network (Vnet).
</p>
<br />

<p>
<img src="https://images2.imgbox.com/1f/4c/cWFvMGCp_o.png" alt="imgbox"/><br />
<img src="https://thumbs2.imgbox.com/26/af/Gboy1qGC_t.png" alt="image host"/></a>
</p>
Step 2: After your VM is created, you need to connect to it. Click on your virtual machine and locate the public IP address. You will connect to your machine using Remote Desktop Connection. Copy this address and open up the remote desktop connection. Paste the public IP address and select connect.
</p>
<br />

<p>
<img src="https://images2.imgbox.com/43/58/8iHFOb8d_o.png" alt="image host"/><b /><img src="https://images2.imgbox.com/ea/26/EheoO4J8_o.png" alt="image host"/></a>
</p>
<p>
Step 3: Now we need to install/enable IIS on your VM. Right click on the start button, choose run. Inside the run box type: control. Once your control panel opens click on programs, then turn Windows features on or pff.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
