<h2>Description</h2>
In this section, I'll be configuring logging and monitoring for VMs by creating an Azure Storage Account to store the Network Security Group flow logs and linking them to the Log Analytics Workspace. 

<h2>Requirements</h2>
- windows-vm running<br> 
- linux-vm running<br> 
- Azure Storage Account<br>

<h2>Azure Storage Account</h2>
Create the Azure Storage Account and come up with a unique name. All the settings are left at default. 

![image](https://github.com/user-attachments/assets/f32918f4-d605-4992-9217-23731d459d3b)

<h2>Network Security Groups Flow Logs</h2>
Start enabling the flow logs for the VMs by navigating to Network Security Groups > windows-vm > Monitoring > NSG flow logs > Create flow log. Both flow logs will be created, so whether windows-vm or linux-vm is chosen doesn't matter. Click on Select target resource. 

![image](https://github.com/user-attachments/assets/d849c88c-e602-4406-8ff1-78ccd1d176cd)

Select both resources, confirm selection, and set the retention days to 60. 

![image](https://github.com/user-attachments/assets/2f9c53a3-b2f3-4bd1-82fe-b431d8fda025)

![image](https://github.com/user-attachments/assets/d62bd410-1816-4c58-82d0-cbfca0b361bb)

Navigate to Analytics and enable traffic analytics. Set the traffic processing interval to 10 minutes and ensure the proper workspace is selected. Review and create. 

![image](https://github.com/user-attachments/assets/0bbc76b5-407c-4faf-8427-8221989d8c6a)

<h2>Microsoft Sentinel</h2>
Navigate to Microsoft Sentinel > Content management > Content hub. Install Windows Security Events and Syslog.

![image](https://github.com/user-attachments/assets/2d585042-a04a-4bfa-88cf-8691bef406b5)

![image](https://github.com/user-attachments/assets/7cb2106f-831c-4cb1-afbc-37ade39272ae)

When Windows Security Events is installed, click on Manage, check Windows Security Events via AMA, and click on open connector page. 

![image](https://github.com/user-attachments/assets/aa97bbd7-217e-4a80-a759-d39611df3704)

Click on create data collection rule. 

![image](https://github.com/user-attachments/assets/783b19d8-509d-4128-9c77-d6cbe89d274f)

![image](https://github.com/user-attachments/assets/98b4d22a-94d9-4d3e-8f7b-fc2d5c5a6bf1)

![image](https://github.com/user-attachments/assets/9b5af7fe-50b7-42c9-8f61-d58ad633f691)

![image](https://github.com/user-attachments/assets/9be46f14-e900-4d66-b96f-3e03dd868a2e)

Perform the same tasks for Syslogs. 

![image](https://github.com/user-attachments/assets/94fb4663-f4a4-4d86-8026-25a77fb2080c)

![image](https://github.com/user-attachments/assets/7127fdcf-2090-4af8-a903-72504db8f979)

![image](https://github.com/user-attachments/assets/ab6b9e66-65e8-4c52-ae58-c42b7843ef9d)

![image](https://github.com/user-attachments/assets/aa48ed3b-c094-4f31-bb30-2688d2511a65)

On the Collection tab, set the minimum log level of LOG_AUTH to LOG_DEBUG.

![image](https://github.com/user-attachments/assets/60caaf99-46b1-4a8c-ba04-ab8d4a962ee3)

We can now check logs are being ingested correctly by querying logs for both machines.

![image](https://github.com/user-attachments/assets/af8ee221-d9b9-403f-8cd8-7add3ebfd167)

![image](https://github.com/user-attachments/assets/d057f529-8e6b-4fd1-9c44-eb32756c3beb)

![image](https://github.com/user-attachments/assets/3297665e-0533-4f74-b4e4-a80a9701c2ec)
