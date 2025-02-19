<h1>Installing MS SQL Server</h1>

<h2>Description</h2>

In this section, I will install MS SQL Server on the virtual machines so the attackers have something to break into and generate application logs. 

<h2>Requirements</h2>

- <a href="https://www.microsoft.com/en-us/evalcenter/download-sql-server-2019?msockid=0a45c374f57968f21b54d6ecf47d69d1">SQL Server</a>
- <a href="https://learn.microsoft.com/en-us/ssms/download-sql-server-management-studio-ssms">SQL Server Management Studio</a>

<h2>Windows VM</h2>

I remote into the Windows VM using Remote Desktop Connection to get started. Download SQL Server and click on Download Media.

![image](https://github.com/user-attachments/assets/dfb5ada8-3d47-479d-aa9d-4ed50b26328d)

Download the ISO and when that is done, mount it and click on setup. The following windows opens to start installing the sql server. 

Click on the first option.

![image](https://github.com/user-attachments/assets/4b493366-9b49-4d4b-89e7-b92427910de6)

Mostly everything is kept at default up until this point. Click on Database Engine Server.

![image](https://github.com/user-attachments/assets/e77033b5-183e-4241-966a-b4da9cf88dc5)

In the database configuration, select the radio button for mix mode and set a password for the system admin (I use the same one for the VMs, these are honeynets so weak password policies are fine). The current windows user is also added
as an admin. After this page is the install page to wrap up the process.

![image](https://github.com/user-attachments/assets/fdb74b18-953b-447a-953f-f73199aba111)

Next install SSMS to have a user interface to use the SQL Server. 

Logging needs to be enabled for the SQL Server, this is done in Registry Editor. Follow the path shown at the top and add Network Service and give it full control. 
<a href="https://learn.microsoft.com/en-us/sql/relational-databases/security/auditing/write-sql-server-audit-events-to-the-security-log?view=sql-server-ver16">Reference.</a>

![image](https://github.com/user-attachments/assets/de12a9a6-c892-4b44-933b-0d2f827e118f)

![image](https://github.com/user-attachments/assets/fbb6288e-6cb2-45b6-a109-9646b607333f)

Login to SSMS and change the settings to SQL Server Authentication and Optional.

![image](https://github.com/user-attachments/assets/cc0bd9ab-936e-4185-86ce-21da286a6b09)

Right click on ther server and go to properties to enable both successful and failed logins attempts. Restart the server afterwards.

![image](https://github.com/user-attachments/assets/017ab330-9b5c-4101-bb8f-326a37f4f748)

Disconnect from the server and reconnect with a wrong password to test if a log is generated. Checking the application logs I can see that a failed login attempt was generated.

![image](https://github.com/user-attachments/assets/c7275c03-fd5d-4e92-907d-fe99fb089253)

Lastly, turn off Windows Firewall.

![image](https://github.com/user-attachments/assets/f690d924-0210-40d3-8040-3c6d6c19cff7)

<h2>Linux VM</h2>

Ping the linux machine and if replies are received, continue to SSH into it.

![image](https://github.com/user-attachments/assets/aaef98df-f9d5-4ee2-96a9-73b15e52a9b8)

The machines are working as inteded, so this section of the lab is wrapped up. 
