<h1>Microsoft Entra ID</h1>

In Microsoft Entra ID, create three users and assign the roles Tenant-Level Global Reader, Subscription Reader, and Resource Group Reader. 

<h2>Users</h2>

- globalreaderjohn
- subreaderjane
- rgcontributordave

<h2>Tenant-Level</h2>
Create globalreaderjohn. 

![image](https://github.com/user-attachments/assets/887cb1a5-f46b-4b8f-b06d-b6c3fc70b4bb)

Navigate to Assigned roles > Add assignments. Search Global Reader and assign. 

![image](https://github.com/user-attachments/assets/9ab6e616-69d9-44ae-9c28-38307ab4e3d2)

<h2>Subscription Level</h2>
Create subreaderjane.

![image](https://github.com/user-attachments/assets/7d6f8527-5047-4397-9695-cc4cd5700c2a)

Navigate to Subscriptions > (Subscription Name) > Access control (IAM) > add role assignment. 

![image](https://github.com/user-attachments/assets/0553b71e-5c10-4fbf-9b09-5a806184387d)

Select member and select the user granted the reader role, subreaderjane. 
![image](https://github.com/user-attachments/assets/c64147cf-83ac-4059-a0cc-6aee4ce75780)

<h2>Resource Level</h2>

Create rgcontributordave.

![image](https://github.com/user-attachments/assets/27807096-cfaf-4aa3-824d-d82af205f7bd)

Create a new resource group so that RG-Home-Lab doesn't mess up. I'll name it Permissions-Tester. Navigate to Resource Groups > Permissions-Tester > Access control (IAM) > add role assignment. 

![image](https://github.com/user-attachments/assets/c1d24aa5-b12c-4d8a-a4d7-293a081db781)

Select Privileged administrator roles and select Contributor.

![image](https://github.com/user-attachments/assets/7ed0ef62-a7a1-4c78-8002-b99b48de2cab)

Select members, find rgcontributordave, and assign the role. 

![image](https://github.com/user-attachments/assets/f4c58a56-86cb-4c1b-87e6-9a1e08cae630)
