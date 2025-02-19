<h1>Creating the Honeynet</h1>

<h2>Description</h2>
In this section, I will go over creating and configuring the honeynet I use for the home lab.

<h2>Requirements</h2>
- Azure Subscription<br>
- Windows Virtual Machine<br>
- Linux Virtual Machine<br>

<h2>Azure Subcription</h2>
An Azure Subscription is needed to create the honeynet. You can sign up for one <a href="https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account">here.</a>

<h2>Honeynet</h2>

The first virtual machine will be Windows 10 with the following configuration. The resource group "RG-Home-Lab" is what I will be using throughout the lab, along with the virtual network "Lab-VNet." 

![image](https://github.com/user-attachments/assets/9c533f15-2978-4c17-a243-801176c4e329)

![image](https://github.com/user-attachments/assets/a244758c-93e1-4462-832a-c8f8913bca9b)

The next virtual machine will be Linux using Ubuntu. The exact configuration used for the Windows VM applies to this one. The only difference is changing the authentication method to a password instead of an SSH key and using an Ubuntu Server image.

<h2>Network Security Group</h2>

A firewall rule to allow all inbound traffic needs to be created for both machines. This is done by searching Network Security Group and clicking the NSG for our desired resource. In this case, windows-vm and linux-vm. First, remove the RDP rule from both machines.

![image](https://github.com/user-attachments/assets/a985b83a-c2f0-4d68-b6e0-11c169722fbc)

Then, you can just navigate to Setting > Inbound Security Rules to create the rule needed. The settings used for this NSG are the same as for the Linux NSG.

![image](https://github.com/user-attachments/assets/fe1bd3ea-7fa4-413b-bdcb-7a976023384c)

