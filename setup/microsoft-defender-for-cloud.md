<h2>Description</h2>
Enabling Microsoft Defender for Cloud will allow us to ingest logs from the virtual machines into Log Analytics Workspace.

<h2>Requirements</h2>
- Windows VM Running<br>
- Linux VM Running<br>
- Log Analytics Workspace<br>
- Microsoft Sentinel<br>

<h2>Microsoft Defender for Cloud</h2>
Navigate to Management > Environmental Settings and click on the Log Analytics Workspace created.

![image](https://github.com/user-attachments/assets/2f55d9ac-a271-49c1-a99b-c18109ada6af)

Enable Servers for the VMs and SQL servers on machines for the SQL server added to windows-vm, this allows the collect logs from the VMs and the SQL server in windows-vm. Save the current plans.

![image](https://github.com/user-attachments/assets/2ef9fd4c-e275-44cb-b2aa-e3990314410c)

Navigate to Data Collection, select All Events, and save. 

![image](https://github.com/user-attachments/assets/9a833393-35cb-43f8-abee-9995f180d667)

Now that Microsoft Defender for Cloud is enabled for LAW-Home-Lab, the next step is to enable it for the Azure subscription. 

Enable Servers, Storage Accounts, Key Vault and Databases. Save the current plans. 

![image](https://github.com/user-attachments/assets/cef54c52-4eee-4fdc-aefc-451c6437f64f)

Navigate Settings > Continuous Export > Log Analytics workspace and select all the options for Export data types.

![image](https://github.com/user-attachments/assets/ba02dfc1-b1eb-41d9-a53f-49f96b26e496)

Select the correct Resource group and workspace, RG-Home-Lab and LAW-Home-Lab. Save the current settings for continuous export. 

![image](https://github.com/user-attachments/assets/08a2872f-d9b3-4706-8de1-0ee03a7bc43a)
