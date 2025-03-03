<h2>Description</h2>
This section will cover enabling NIST SC-7 by configuring Azure Private Link and Firewall for Azure Key Vault and Azure Storage Account instances.

<h2>Azure Key Vault</h2>
Navigate to Key Vaults > the key vault instance used in the lab > Networking, disable public network access and allow trusted Microsoft services to access this resource. Save.

![image](https://github.com/user-attachments/assets/15d2cad7-e2f4-4e7d-b064-0cb637e47745)

Create a Private Endpoint. 

![image](https://github.com/user-attachments/assets/6f6f54f1-2e65-4c16-a895-d2bad8ef725e)

![image](https://github.com/user-attachments/assets/d11698ad-8c4e-43f5-935a-00131781841a)

![image](https://github.com/user-attachments/assets/91b69d24-fad2-4f95-9a27-56d2ad66cb88)

![image](https://github.com/user-attachments/assets/12f508ce-bba6-4006-9855-21d9228d61b5)

![image](https://github.com/user-attachments/assets/bdc0fef9-aaa5-4299-9a9c-cdf3015591de)

![image](https://github.com/user-attachments/assets/5abb4fc5-d63b-4b72-b158-2c153e3e8460)

<h2>Storage Account</h2>
You can just navigate to the storage account used in the lab and go to configuration to disable Blob anonymous access.

![image](https://github.com/user-attachments/assets/2fb4bb3f-da88-4c66-9365-c3e458212f91)

Disable Public network access.

![image](https://github.com/user-attachments/assets/a441424a-b6b5-487a-8614-db940041f957)

Create the Private Endpoint.

![image](https://github.com/user-attachments/assets/80254f6b-f4ed-4375-a2be-f9ff45309010)

![image](https://github.com/user-attachments/assets/f11c1cf3-2350-416c-aaee-701d259eab09)

![image](https://github.com/user-attachments/assets/8b4a5cc6-41c0-4b12-924e-9db10fa3a6a6)

![image](https://github.com/user-attachments/assets/42ce8cba-4414-48bb-bebb-82a78e33887a)

