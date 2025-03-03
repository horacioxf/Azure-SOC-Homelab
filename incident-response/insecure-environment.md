<h2>Description</h2>
Allow the virtual machines to run for 48 hours and collect the metrics for how many incidents occurred. 

<h2>Querying Metrics</h2>
Use the following query to collect the information for the start and stop times.

<code>range x from 1 to 1 step 1
| project StartTime = ago(48h), StopTime = now()
</code>

![image](https://github.com/user-attachments/assets/8e0f07ce-d948-448d-b536-2d643ec06dfc)

Use the following query to collect the amount of SecurityEvent logs generated.

<code>
SecurityEvent
| where TimeGenerated >= ago(48h)
| count
</code>

![image](https://github.com/user-attachments/assets/e5496549-9999-4089-a292-7b8734a10ddd)

Use the following query to collect the amount of Syslogs logs generated.

<code>
Syslog
| where TimeGenerated >= ago(48h)
| count
</code>

![image](https://github.com/user-attachments/assets/6c21fd3e-05ad-4bf6-b359-d40f1c14aca2)

Use the following query to collect the amount of SecurityIncident logs generated.

<code>
SecurityIncident
| where TimeGenerated >= ago(48h)
| count
</code>

![image](https://github.com/user-attachments/assets/3afa5f68-04ef-4c09-8c9a-718259cc6178)

Use the following query to collect the amount of NSG Inbound Malicious Flows Allowed

<code>
AzureNetworkAnalytics_CL 
| where FlowType_s == "MaliciousFlow" and AllowedInFlows_d > 0
| where TimeGenerated >= ago(48h)
| count
</code>

![image](https://github.com/user-attachments/assets/f5ad843b-8ea2-49c2-ac47-598b2ae65338)


## Metrics Before Hardening / Security Controls

The following table shows the metrics measured in the insecure environment for 48 hours:

| Start Time               | Stop Time
| ------------------------ | -----
|2025-03-01T02:30:00.7013311Z       | 2025-03-03T02:00:34.5423555Z

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent (Windows VM)            | 52067
| Syslog (Linux VM)                  | 21544
| SecurityIncident (Security Incidents)        | 240
| AzureNetworkAnalytics_CL (NSG Inbound Malicious Flows Allowed) | 1965

<h2>Attack Maps</h2>
The following attack maps are attacks within the last 48 hours.

![image](https://github.com/user-attachments/assets/9ac4eb8d-9550-43ed-82c7-e1d3adcd0627)

![image](https://github.com/user-attachments/assets/04b486cf-86c2-4a2d-a193-e5191389feac)

![image](https://github.com/user-attachments/assets/c48a9b49-a353-48d2-a0f5-0fb9a38871d3)

![image](https://github.com/user-attachments/assets/eb5f043b-84d2-46db-a4be-23395e08d150)
