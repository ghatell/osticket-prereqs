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

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/user-attachments/assets/19703132-de8f-4ccf-bb21-1be2b3cc8a03" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This project demonstrates the installation and configuration of osTicket on an Azure Windows 10 Virtual Machine. First, an Azure Virtual Machine named osticket-vm was created. The VM was accessed using Remote Desktop with the credentials labuser and osTicketPassword1!. After logging into the VM, the osTicket-Installation-Files.zip file was downloaded and unzipped to the desktop for use in the installation process.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/2ff9616d-366f-4381-ae4f-e95c0f5e16dd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first step was to enable IIS (Internet Information Services) with the CGI feature by navigating to the Windows Features settings. Next, several components were installed from the osTicket-Installation-Files folder: PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi), the IIS Rewrite Module (rewrite_amd64_en-US.msi), and the Visual C++ Redistributable (VC_redist.x86.exe). The PHP runtime was configured by creating a directory at C:\PHP and extracting php-7.3.8-nts-Win32-VC15-x86.zip into it. Additionally, MySQL 5.5.62 was installed using the typical setup, with the root user configured with the credentials root/root.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/25c6e147-3605-4a8c-acf0-a3060c427390" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
IIS was then configured to use PHP by registering C:\PHP\php-cgi.exe through the PHP Manager in IIS, followed by restarting the IIS server. The osTicket application was installed by unzipping osTicket-v1.15.8.zip and copying the upload folder to C:\inetpub\wwwroot, where it was renamed to osTicket. After restarting IIS, the application was accessed via the browser, and required PHP extensions (php_imap.dll, php_intl.dll, and php_opcache.dll) were enabled using the PHP Manager.
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/e18fa717-fcf8-49fa-9f0d-7cbe282498c9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The ost-config.php configuration file was prepared by renaming ost-sampleconfig.php to ost-config.php and assigning appropriate permissions by disabling inheritance, removing existing permissions, and granting full access to "Everyone." HeidiSQL was then installed to create a MySQL database named osTicket, which was used during the final osTicket setup in the browser. The setup process involved specifying the helpdesk name, default email address, and database credentials (osTicket, root, root).
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/4922ef16-24b8-476e-8fc1-3bbfe459bc27" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upon successful installation, the admin panel was accessible at http://localhost/osTicket/scp/login.php, and the end-user portal was available at http://localhost/osTicket/. This project showcases the complete installation and configuration of osTicket in a Windows environment, ready for use as a helpdesk solution.
</p>
<br />
