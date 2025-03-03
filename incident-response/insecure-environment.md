<h2>Description</h2>
Allow the virtual machine to run for 24 hours and collect the metrics for how many incidents occurred. 

<h2>Querying Metrics</h2>
Use the following query to collect the information for the start and stop times.

<code>range x from 1 to 1 step 1
| project StartTime = ago(24h), StopTime = now()
</code>

![image](https://github.com/user-attachments/assets/991d2145-9884-4d46-9bc4-4f411ce02b10)

Use the following query to collect the amount of SecurityEvent logs generated.

<code>
SecurityEvent
| where TimeGenerated >= ago(24h)
| count
</code>

![image](https://github.com/user-attachments/assets/2090e197-8ba2-49c1-bc24-783d45875533)

Use the following query to collect the amount of Syslogs logs generated.

<code>
Syslog
| where TimeGenerated >= ago(24h)
| count
</code>

![image](https://github.com/user-attachments/assets/2cbe93db-ee83-4e21-ab48-43914271584c)

Use the following query to collect the amount of SecurityIncident logs generated.

<code>
SecurityIncident
| where TimeGenerated >= ago(24h)
| count
</code>

![image](https://github.com/user-attachments/assets/7fd6bdce-52c4-40f6-9ea1-67a043d481d6)

Use the following query to collect the amount of NSG Inbound Malicious Flows Allowed

<code>
AzureNetworkAnalytics_CL 
| where FlowType_s == "MaliciousFlow" and AllowedInFlows_d > 0
| where TimeGenerated >= ago(24h)
| count
</code>

![image](https://github.com/user-attachments/assets/9f3ecc8a-d575-4f08-b952-78dea51b5d58)
