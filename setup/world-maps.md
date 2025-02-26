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

At the moment, mssql has no logs 
