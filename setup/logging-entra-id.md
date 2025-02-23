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
