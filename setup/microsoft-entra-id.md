<h1>Microsoft Entra ID</h1>

In Microsoft Entra ID, create three users and assign the roles Tenant-Level Global Reader, Subscription Reader, and Resource Group Reader. 

<h2>Users</h2>

- globalreaderjohn
- subreaderjane
- rgcontributordave

<h2>Tenant-Level</h2>
Create globalreaderjohn. 

![image](https://github.com/user-attachments/assets/8f6f3fa6-aa29-42b6-a379-641a3ed4b6b1)

Navigate to Assigned roles > Add assignments. Search Global Reader and assign. 

![image](https://github.com/user-attachments/assets/9ab6e616-69d9-44ae-9c28-38307ab4e3d2)

<h2>Subscription Level</h2>
Create subreaderjane.

![image](https://github.com/user-attachments/assets/a4ba0aeb-a7a4-444e-9295-1d2b4e92b2fc)

Navigate to Subscriptions > (Subscription Name) > Access control (IAM) > add role assignment. 

![image](https://github.com/user-attachments/assets/0553b71e-5c10-4fbf-9b09-5a806184387d)

Select member and select the user granted the reader role, subreaderjane. 
![image](https://github.com/user-attachments/assets/c64147cf-83ac-4059-a0cc-6aee4ce75780)

<h2>Resource Level</h2>

Create rgcontributordave.

![image](https://github.com/user-attachments/assets/4be80489-b500-4780-93d6-5311e2e7f483)

Create a new resource group so that RG-Home-Lab doesn't mess up. I'll name it Permissions-Tester. Navigate to Resource Groups > Permissions-Tester > Access control (IAM) > add role assignment. 

![image](https://github.com/user-attachments/assets/c1d24aa5-b12c-4d8a-a4d7-293a081db781)

Select Privileged administrator roles and select Contributor.

![image](https://github.com/user-attachments/assets/7ed0ef62-a7a1-4c78-8002-b99b48de2cab)

Select members, find rgcontributordave, and assign the role. 

![image](https://github.com/user-attachments/assets/f4c58a56-86cb-4c1b-87e6-9a1e08cae630)

<h2>Testing</h2>
Now that the users have been created and the roles have been assigned, I can log in as the users and observe their permissions.

First will be user globalreaderjohn. Logged in as globalreaderjohn, the user can view other users but cant make any changes. Edit properties and Delete are greyed out. 

![image](https://github.com/user-attachments/assets/b6c5d9c8-5cb6-40c8-81a7-08623a681613)

Next is subreaderjane. After logging in as subreaderjane, I can look at the subscriptions, but I can't make changes, like delete.

![image](https://github.com/user-attachments/assets/be2bb913-52f1-4572-9758-78c3bd29693c)

![image](https://github.com/user-attachments/assets/453724c1-b5ea-4506-b3f8-5ac8b8c90959)

Lastly, rgcontributordave. Logging in as rgcontributordave, I'll delete the resource group created earlier, Permissions-Tester

![image](https://github.com/user-attachments/assets/eab2489f-012e-48f9-83e6-50cfb00a943f)

![image](https://github.com/user-attachments/assets/edd56f47-0d44-44bd-935a-a46d21f45cde)
