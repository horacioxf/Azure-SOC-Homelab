<h2>Description</h2>
This section will provide an overview of performing an incident response using NIST 800-61 Incident Response Lifecycle. The Preparation phase will be skipped because it was already performed here <a href="https://github.com/horacioxf/Azure-SOC-Homelab/blob/main/incident-response/insecure-environment.md">insecure_environment.md</a>.

<h2>Detection & Analysis</h2>
Navigate to Microsoft Sentinel > Threat Management > Incidents. The first incident is a CUSTOM: Brute Force ATTEMPT - Windows alert. I assign the Incident to myself, set the status to Active, and keep the Severity at Medium. 

![image](https://github.com/user-attachments/assets/0bb1a98c-26f0-41dd-a825-5850f40163ff)

I navigate to Full Details and click on Activity Log; the incident was created by an alert on 03/02/25 at 08:52 PM. 

![image](https://github.com/user-attachments/assets/7d43ea64-890d-40fa-85f8-b94588276570)

Looking at the Entities tab, six entities registered a log activity. Five are IP addresses, and the sixth is the windows-vm host itself. 
Because the incident I assigned to myself happened at 08:52 PM, the IP address I'm interested in is "194.0.234.44". 
The geolocation information from this IP address tells me it's coming from the city of Sundon from Central Bedfordshire in the United Kingdom. 

![image](https://github.com/user-attachments/assets/05201dd2-c8b7-4576-aace-359f656dd665)

![image](https://github.com/user-attachments/assets/88e3d84e-a4ac-483d-a8e7-436a6a6e10f3)

I began investigating the incident by clicking the Investigate button to continue determining the scope. I see that attacker "194.0.234.44" is involved in two other brute-force attempt incidents.

![image](https://github.com/user-attachments/assets/45fc13a3-34ee-4987-a641-135abfefe413)

To determine whether this is a true positive, I use this query to investigate the attacker further: "194.0.234.44."

<code>
// Failed logon 
SecurityEvent
| where EventID == 4625
| summarize FailureCount = count() by AttackerIP = "194.0.234.44", EventID, Activity, DestinationHostName = Computer
| where FailureCount >= 10
</code>

Within 48 hours, the attacker tried to log in 89972 times. Concluding that this is a true positive.

![image](https://github.com/user-attachments/assets/74e03d31-2022-40eb-935c-b952c9524940)

![image](https://github.com/user-attachments/assets/6aabdac1-2161-4e18-acec-a657021b99e9)

<h2>Containment, Eradication and Recovery</h2>
To ensure this incident doesn't occur again, I'll lock down the Network Security Groups assigned to the Virtual Machines/Subnets to only allow necessary traffic.
Navigate to the VMs, and in the Network Settings, add a new inbound rule that only allows traffic from a specific IP address on both VMs. Delete the DANGER inbound rule created that allows any traffic. 

![image](https://github.com/user-attachments/assets/fb8affb7-bf72-45b4-a467-94526baf621d)

![image](https://github.com/user-attachments/assets/7240ee66-0129-4a47-8aaa-e85803bc3a69)
