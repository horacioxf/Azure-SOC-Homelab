<h2>Description</h2>
This section will cover Log Analytics Workspace and Microsoft Sentinel, and geoip-summarized.csv will be used to see where the attacks are coming from. 

<h2>Requirements</h2>
- <a href="https://github.com/user-attachments/files/18911480/geoip-summarized.csv">geopip-summarized.csv</a>

<h2>Log Analytics Workspace</h2>
When creating the LAW, everything will be set to the default setting. The workspace I'll be using will be named LAW-Home-Lab. Workspaces must have unique names, so workspaces with the same name can't exist unless they are something like LAW-Home-Lab01 and LAW-Home-LAB02. 

<h2>Microsoft Sentinel</h2>
When creating Microsoft Sentinel, add the workspace that was created. Making this connection will allow Microsoft Sentinel to use the CSV file and visualize the source of the attacks.

![image](https://github.com/user-attachments/assets/3ab60942-545f-4f6c-88d6-308e0586d410)

Click on the workspace and navigate to Configuration > Watchlist > New to create the geoip watchlist with the following settings. 

![image](https://github.com/user-attachments/assets/94d0e7aa-9a69-43f9-8adf-c671ba60acbe)

![image](https://github.com/user-attachments/assets/ddeacb77-d729-4b3a-85c5-3b8bfaef08db)

![image](https://github.com/user-attachments/assets/3ca32371-e6af-4f1b-9323-75cb991f72a0)
