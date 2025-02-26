<h2>Description</h2>
This section will go over creating workbooks in Microsoft Sentinel to demonstrate malicious traffic worldwide.

<h2>Requirements</h2>
- VMs running<br>
- <a href="https://github.com/user-attachments/files/18989639/windows-rdp-auth-fail.json">windows-rdp-auth-fail.json</a><br>
- <a href="https://github.com/user-attachments/files/18989653/nsg-malicious-allowed-in.json">nsg-malicious-allowed-in.json</a><br>
- <a href="https://github.com/user-attachments/files/18989658/linux-ssh-auth-fail.json">linux-ssh-auth-fail.json</a><br>
- <a href="https://github.com/user-attachments/files/18989662/mssql-auth-fail.json">mssql-auth-fail.json</a><br>

<h2>Constructing World Maps</h2>
Navigate to Microsoft Sentinel > Threat management > workbooks > add workbooks to create the world maps. 

![image](https://github.com/user-attachments/assets/43e385a3-e79e-49d6-a8f4-1f9f6f4b1c43)

Edit the default workbook created and remove the elements already in it so that there is a blank fresh start. Click on Add > add query > advance editor. 

![image](https://github.com/user-attachments/assets/70b0dd30-c0ef-4a7a-8ed0-f60fae147c03)

![image](https://github.com/user-attachments/assets/21276d5d-f43f-4e86-9a8e-c6853af5195d)

![image](https://github.com/user-attachments/assets/b6af2839-5345-497e-8370-eb1b56c0176b)

![image](https://github.com/user-attachments/assets/4ff657df-c192-4a43-816d-f48c9424d82a)

Replace the query item with the content in linux-ssh-auth-fail.json, click on done editing, save and rename.

![image](https://github.com/user-attachments/assets/da37e37c-0392-49c2-91a8-b5ba3fc14a39)

![image](https://github.com/user-attachments/assets/efc21431-d9a2-4da4-bbfe-fa06175baf47)

![image](https://github.com/user-attachments/assets/1d04e34f-9acc-44af-b353-f109fa265dd1)

Repeat the process for the remaining three workbooks. 

![image](https://github.com/user-attachments/assets/799b42a1-ff22-41f0-9e01-90fba1456290)

![image](https://github.com/user-attachments/assets/af1e56fa-2693-49fa-a477-c543faae354d)

![image](https://github.com/user-attachments/assets/267ed5af-e652-4029-9ea3-34681ed1875f)

mssql-auth-fail has no logs. There was an issue where it wasn't querying Event logs. I had to create a new Data Collection Rule with both VMs.

![image](https://github.com/user-attachments/assets/a04b229d-b3c9-4bb1-bbae-abd730f02d53)

![image](https://github.com/user-attachments/assets/f5e61e13-ec73-45d0-847f-8753e3b42d5a)

![image](https://github.com/user-attachments/assets/1b187463-0ecb-427b-a412-c57b9c85f5f4)

Add the following custom logs. <br>
<code>Microsoft-Windows-Windows Defender/Operational!*[System[(EventID=1116 or EventID=1117)]]
Microsoft-Windows-Windows Firewall With Advanced Security/Firewall!*[System[(EventID=2003)]]
Application!*[System[(EventID=18456 or EventID=18454)]]</code>

![image](https://github.com/user-attachments/assets/cf6d1761-2e1f-4c66-bf0a-c8734c48b045)

![image](https://github.com/user-attachments/assets/6b0aea58-873b-4af4-a7c6-109afae7536a)

Set the destination to the Log Analytic Workspace and add the data source for the windows-vm.

![image](https://github.com/user-attachments/assets/76a20161-e3b3-4c29-811f-5a77e095f0f4)

Create the data source for the linux-vm and set the destination.

![image](https://github.com/user-attachments/assets/9435a506-67b6-477b-8cfb-a0188cb389df)

Review and create.

The event logs and the world map now populate.

![image](https://github.com/user-attachments/assets/667c5b30-0dfb-415e-9262-7e86703ea006)

![image](https://github.com/user-attachments/assets/54d118e6-0ba1-412c-803c-217ecf6c5214)
