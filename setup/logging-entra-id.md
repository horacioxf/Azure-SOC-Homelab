<h2>Description</h2>
Configure active directory logging in Microsoft Entra ID at the tenant, subscription, and resource levels. 

<h2>Requirements</h2>
- Users at tenant level, subscription level, and resource level. <a href="https://github.com/horacioxf/Azure-SOC-Homelab/blob/main/setup/microsoft-entra-id.md">Example.</a>

<h2>Tenant Level</h2>
Navigate to Microsoft Entra ID > Diagnostic settings > Add diagnostic setting and enable AuditLogs and SignInLogs.

![image](https://github.com/user-attachments/assets/efdd7aeb-1787-42fe-a1f2-3196968a73dc)

Configure the destination details to the correct subscription and log analytics workspace.

![image](https://github.com/user-attachments/assets/55fe3e47-e6fd-41e7-9b01-1435271e2b85)

The tables are created in Log Analytics Workspace for AuditLogs and SignInLogs.

![image](https://github.com/user-attachments/assets/6bd3e7ed-d7ab-4420-aa43-44b8a255c08b)

![image](https://github.com/user-attachments/assets/5929f401-f79d-431a-bacd-b8cd37a9383b)

To generate logs and ensure AuditLogs and SignInLogs are working correctly, I'll create a user called test_user, login, and assign the Global Admin role.

![image](https://github.com/user-attachments/assets/673275ba-6b64-4ec6-8386-843e0deb57a6)

![image](https://github.com/user-attachments/assets/64b0290a-a67f-493e-b86d-42758da8f02c)

![image](https://github.com/user-attachments/assets/d8fac2f1-d47f-4100-bb83-dac74570d6d7)

The following results appear when querying SignInLogs and AuditLogs.

![image](https://github.com/user-attachments/assets/ae6a96e6-d0dc-4dd1-82d9-753e0f4dffea)

![image](https://github.com/user-attachments/assets/525339d4-4ca0-49e6-808b-9cf36dd1353f)

<h2>Subscription Level</h2>
Navigate to Monitor > Activity Logs > Export Activity Logs to export the activity logs to Log Analytics Workspace.

![image](https://github.com/user-attachments/assets/e4a8c5ee-6a09-4832-b49a-19520cbc4e10)

![image](https://github.com/user-attachments/assets/d6697e12-f0ec-4fd2-a6e1-1aef1398f1a0)

![image](https://github.com/user-attachments/assets/b1d95b4a-2b14-4b2a-9c62-93dd0866d3a1)

To test the logs, create two new resource groups and delete them once they are created. The test resource groups for this are Doe-Resource-Group and Jane-Economic-Infrastructure.

<code>AzureActivity
| where ResourceGroup startswith "Jane"
| order by TimeGenerated
</code>

This is used to query for deletion of resource groups that start with "Jane"

![image](https://github.com/user-attachments/assets/ea63c20a-8177-440a-9a59-d1e280eff0c9)

<code>AzureActivity
| where OperationNameValue endswith "DELETE"
| where ActivityStatusValue == "Success"
| where TimeGenerated > ago(30m)
| order by TimeGenerated
</code>

This is used to query for deletion activity within a certain lifespan. 

![image](https://github.com/user-attachments/assets/d836dbc7-d7b4-400b-b1b2-7e4e309422ef)

<h2>Resource Level</h2>
