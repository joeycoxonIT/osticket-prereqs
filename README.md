<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Virtual Machine in Azure
- Install osTicket
- Install HeidiSQL
- Install MySQL
- Install PHP
- Install Microsoft C++ Redistributable

<h2>Installation Steps</h2>
<p>
Start by typing “virtual machines” in the search bar at the top of the page, then select “virtual machines” under “services”.
</p>
<p>
<img src="https://i.imgur.com/x59vW1j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
After you’ve done so, you’re at the page that allows you to create a virtual machine. Select “create” -> “Azure virtual machine”.
</p>
<p>
<img src="https://i.imgur.com/dELhKYF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />

<p>
Now we will set up the resource group along with the virtual machine. For this tutorial, we’ll name the resource group “osTicket” and the virtual machine “osticket-vm”. Also create a username and password. For the image setting, select “Windows 10 Pro, Version 22H2, x64 Gen2”. For the “size” setting, ensure that the virtual machine has 2 vCPUs and 16 GB of memory. The settings on the following pages can remain unchanged, however, make sure to check the licensing box on the first page.
</p>
<p>
<img src="https://i.imgur.com/Y3rtLJK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/8jRR0VY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
After you’ve created the virtual machine, go to the search bar within the task bar at the bottom of your screen and enter “remote desktop connection”. Click on it, then type the virtual machine’s public IP address, which you will find it listed in your virtual machine page in Azure, once that's done, click "Connect".
</p>
<p>
<img src="https://i.imgur.com/Y38Ab5W.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/vdcqREL.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
After you've logged into your Remote Desktop, you can now download the osTicket file linked here: https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0. Copy and paste this link into a browser on your remote desktop. Once this is done, download and unzip the file within your remote desktop.
</p>
<p>
<img src="https://i.imgur.com/opwiQ2P.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Next we will install IIS. Go to the search bar at the bottom of the screen and type in “control panel”. Once you’ve opened the control panel, click “uninstall programs”, then click “turn Windows features on or off”. Scroll to where you see “Internet Information Services”. Make sure it’s checked, then expand it -> “world wide web services” -> “Application Development Features”, then make sure “CGI” is checked. Once this is done, click “OK”.
</p>
<p>
<img src="https://i.imgur.com/FCavJ7u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/bgFZ2T0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/nTycf4j.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
After we’ve installed IIS, now it’s time to install PHP Manager. Go to the “osTicket Installation Files” folder located on your desktop. Then click “PHPManagerforIIS_V1.5.0”. Make sure to agree to terms and conditions. Do the same for “rewrite_amd64”.
</p>
<p>
<img src="https://i.imgur.com/l08fcBY.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/o5di7bH.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Next we will create a PHP directory. Go to the folder icon at the bottom of the screen. Right click it and then select “File Explorer”. Once you’re there, go to “This PC” and then select “Windows (C:), which is your “C” drive. Once you’re in your “C” drive, create a folder and name it “PHP”. Once that’s done, open your “osTicket Installation Files” folder and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder on your "C" drive.
</p>
<p>
<img src="https://i.imgur.com/ObYACAh.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<br />
