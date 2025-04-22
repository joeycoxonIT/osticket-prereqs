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

- Create a Virtual Machine in Azure
- Install osTicket
- Install HeidiSQL
- Install MySQL
- Install PHP
- Install Microsoft C++ Redistributable

<h2>Installation Steps</h2>

<h3>1) Create a Virtual Machine</h3>
<p>
  
- In the search bar at the top of the page, type and select “virtual machines”
- Once you’re at the virtual machines page, select “create” -> “Azure virtual machine”
  - Create a resource group. For this tutorial, we will name it “osTicket”.
  - Name the virtual machine “osticket-vm”
  - Under “Administrator account” create a username and password
  - Under "Image", select “Windows 10 Pro, Version 22H2, x64 Gen2”.
  - "Under "Size", select an option with at least 2 vcpus and 16 GB of memory
  - Once that's done, ensure the licensing box is checked, then click "Review + Create"
</p>
<p>
<img src="https://i.imgur.com/x59vW1j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/dELhKYF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/Y3rtLJK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/8jRR0VY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>2) Connect to the Virtual Machine</h3>
<p>
  
- Go back to the virtual machines page in Azure, then copy the Public IP address
- Go the Windows search bar at the bottom of your screen and open “Remote Desktop Connection”
- Under “Computer” paste the Public IP address then connect to the VM
</p>
<p>
<img src="https://i.imgur.com/Y38Ab5W.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/vdcqREL.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>3) Install osTicket files within the Virtual Machine</h3>
<p>

- To download the osTicket Installation files, copy and paste this link: https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0 into a browser on your remote desktop
- Once that's done, download and unzip the file within your remote desktop.
</p>
<p>
<img src="https://i.imgur.com/opwiQ2P.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>4) Install IIS</h3>
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

<h3>5) Install PHP Manager</h3>
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

<h3>6) Create a PHP directory</h3>
<p>
Next we will create a PHP directory. Go to the folder icon at the bottom of the screen. Right click it and then select “File Explorer”. Once you’re there, go to “This PC” and then select “Windows (C:), which is your “C” drive. Once you’re in your “C” drive, create a folder and name it “PHP”. Once that’s done, open your “osTicket Installation Files” folder and unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder on your "C" drive.
</p>
<p>
<img src="https://i.imgur.com/ObYACAh.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>7) Install remaining files</h3>
<p>

- Next, install the remaining files in the “osTicket Installation Files” folder: “vc_redist.x86” and “mysql-5.5.62-win32”. Note: when installing mySQL, make sure to select “Typical” Setup Type.
</p>
<p>
<img src="https://i.imgur.com/PxNd8RM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/VfjpRSh.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Now that mySQL is installed, make sure “Launch the MySQL Configuration Wizard” is checked and click “Finish”. Once you’re in the Configuration Wizard, make sure “Standard Configuration" is selected and proceed.
</p>
<p>
<img src="https://i.imgur.com/sfYEtHt.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Make sure “Modify Security Settings” is checked and create a password.
</p>
<p>
<img src="https://i.imgur.com/wiWKv4n.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Once your password is created click Next -> Finish.
</p>
<br />

<h3>8) Launch IIS as an Admin</h3>
<p>
  
- Go to the search bar at the bottom left of the screen and search for “Internet Information Services”.
- Once you see it, right click and “Run as administrator”.
</p>
<p>
<img src="https://i.imgur.com/9BVoWWu.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>9) Register PHP Manager</h3>
<p>
  
- Once you are in IIS, click "PHP Manager"
- Click “Register new PHP Version”.
- Click the “...” icon to the right of the search bar.
- Click “This PC” -> “Windows (C:)” -> “PHP”.
- Then select the “php.cgi” file in the “PHP” folder and click "Open". At last, click “OK”.
</p>
<p>
<img src="https://i.imgur.com/ugWZNZd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>10) Reload IIS</h3>
<p>
  
- On the right of the page, you will see three options under “Manage Server”. Click “Stop”.
- Once this is done, wait a moment, then click “Start” to reload the web server.
</p>
<p>
<img src="https://i.imgur.com/ObmJI92.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/tUp91qO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>11) Install osTicket</h3>
<p>

- Open your “osTicket Installation Files” folder and unzip the compressed osTicket folder.
- Then we want to copy the “upload” folder into “c:\inetpub\wwwroot”. To do this, go to your osTicket folder and right-click the “upload” folder and select “Copy”.
- Then go to your file explorer and select “This PC” -> “Windows (C:)” -> “inetpub” -> “wwwroot”. Once you’re in the “wwwroot” folder, paste the “upload” folder.
- Lastly, rename your "upload" folder to "osTicket".
</p>
<p>
<img src="https://i.imgur.com/kiI7RiZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>12) Reload IIS again</h3>
<p>
  
- Open "Internet Information Services (IIS) Manager". Click "Stop", wait a moment, then click "Start".
</p>
<p>
<img src="https://i.imgur.com/ObmJI92.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/tUp91qO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>13) Install osTicket Extensions</h3>
<p>

- Open "Internet Information Services (IIS) Manager" if you closed it from the previous step.
- Click the arrow to the left of “Site”, then do the same for “Default Web Site”. Then click the “osTicket” folder and select “PHP Manager”.
- Once you’re in “PHP Manager”, select “Enable or disable an extension”. Then enable “php_imap.dll”, “php_intl.dll”, and “php_opcache.dll” by right-clicking on them and selecting “Enable”.
</p>
<p>
<img src="https://i.imgur.com/AYOLte4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/JRqrtrJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/7A6yxw7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>14) Launch osTicket Site</h3>
<p>
  
- Load osTicket into a browser using this link: “http://localhost/osTicket/setup/”. If your page looks like what’s displayed below, you’ve followed the steps correctly.
</p>
<img src="https://i.imgur.com/dRYCZd0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>15) Rename "ost-config.php"</h3>
<p>
  
- Go to “File Explorer -> “This PC” -> “Windows (C:)” -> “inetpub” -> “wwwroot” -> “osTicket” -> “include”, then scroll down to where you see the “ost-sampleconfig.php” file and rename it to “ost-config.php”.
- After renaming the file, right-click it and select “Properties” -> “Security” -> “Advanced”, “Disable inheritance”, then “Remove all inherited permissions”
</p>
<br />

<h3>Assign permissions in "ost-config.php"</h3>
<p>

- After renaming "ost-config.php", right-click it and select “Properties” -> “Security” -> “Advanced”, “Disable inheritance”, then “Remove all inherited permissions”
- Next, click “add” under permission entries.
</p>
<p>
<img src="https://i.imgur.com/1W34PVn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Click “Select a principal”
</p>
<p>
<img src="https://i.imgur.com/y3tyIig.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- In the text box above the “Advanced” button, add permissions for admins, then press “OK”. However, for this tutorial, we will allow permissions for “everyone”.
</p>
<p>
<img src="https://i.imgur.com/DLHZtdb.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Select the permissions you want to give. For this tutorial, we will enable “Full Control”.
</p>
<p>
<img src="https://i.imgur.com/mWFI6CJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Once all that’s done, click “Apply” then “OK” at the bottom right of the “permission entries” tab. Then click “OK” in the tab below.
</p>
<p>
<img src="https://i.imgur.com/izaW4lk.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>16) Continue osTicket Setup</h3>
<p>
  
- Go back to the osTicket page in your browser and click “continue”, which will send you to the login info page.
- Create your account (note - the email for your “Admin User” account needs to be different from your “Help Desk User” email).
</p>
<br />

<h3>17) Install HeidiSQL</h3>
<p>

- Once you have entered the login info for both accounts, you will find a third column called “Database Settings”. Before entering anything, go back to the “osTicket Installation Files” folder and install HeidiSQL
</p>
<p>
<img src="https://i.imgur.com/WAFwt0d.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Once that’s done, ensure “Launch HeidiSQL” is checked then click “Finish.”
</p>
<p>
<img src="https://i.imgur.com/S3xwxia.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>

- After you click finish, you will find an updates page. You can click “Skip” for now.
</p>
<br />
<p>
  
- Now that you’re at the “Session manager” page, you want to create a new session. At the bottom left of the page, click “New” then type in your password for “MySQL Server”. Then click “Open” at the bottom of the page.
</p>
<p>
<img src="https://i.imgur.com/52JOnIF.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Now we will create a database called “osTicket”. Right click “Unnamed” then select “Create new” -> “Database”. Once that’s done, name the database “osTicket”
</p>
<p>
<img src="https://i.imgur.com/LmxYaMl.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/qtUIaaC.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<h3>18) Finish osTicket Setup</h3>
<p>

- Finally, go back to your “osTicket installer” page in your browser and enter your MySQL username and password.
- Once this is done, click Install.
</p>
<p>
<img src="https://i.imgur.com/baX0cbT.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Congrats! You have now successfully installed osTicket.
</p>
