# Logging-and-monitoring-in-azure
This section of the project is all about logs in Azure. 
I created a new **log analytics workspace** and set up  logging from the different resources
such as VMs, storage account, and key vault. I did some actions to trigger logs and then utilized KQL to query some logs.

<details><summary>Geo IP Data Ingestion + Log Analytics and Microsoft Sentinal setup</summary><br>
  
  In this lab, I created a data analytics workspace in Azure. I also created a watchlist inside of azure
  sentinal. This watchlist represents a big list of network blocks with corresponding latitude, longtitude, city, and country    name. It will be used to derive geo locations from IP addresses from attackers.

 # **Creating a log analytics workspace (log aggregator)**

  ![image](https://github.com/user-attachments/assets/855e0245-b0be-4a5a-af11-05b25d08ad68)

  ![image](https://github.com/user-attachments/assets/68b32b5c-eae5-44b9-8536-838b74dffb46)<br>

  

#  **Setting up sentinal and connecting it to the log analytics workspace**

  ![image](https://github.com/user-attachments/assets/f2861169-fc84-4bd3-9b50-b5bbc320506e)

  ![image](https://github.com/user-attachments/assets/153836db-039c-46a0-8583-48749434b74c)

  ![image](https://github.com/user-attachments/assets/3ea125e6-219f-4c8c-8a1a-1645f1b6e9f9)<br>

  

 # **Creating a new watchlist**

  ![image](https://github.com/user-attachments/assets/625fa34c-1c9c-481a-b8fb-76d94c6f3543)

  
  ![image](https://github.com/user-attachments/assets/ccb16ed9-0b65-4da5-a231-cd5a4946d128)

  
  ![image](https://github.com/user-attachments/assets/66e114b0-b180-49f1-9e2e-a9a7322dcce4)<br>

  
  

#  **Trying to query in log analytics**

  ![image](https://github.com/user-attachments/assets/aa7713c7-7938-436e-9bd9-0c0ae4809683)

  ![image](https://github.com/user-attachments/assets/37a961c6-ea7c-4148-8069-f1fd0694dd76)
</details>

<details><summary>Enabling Microsoft Defender for Cloud</summary><br>

  In this lab, I enabled **Microsoft Defender for Cloud (MDC)**. MDC gives a high-level overview of azure environment 
  in terms of security. It also allows us to take logs from virtual machines and ingest them into the **Log Analytics Workspace**.

  # Enable MDC for Log Analytics Workspace

  ## **Enable MDC plans for VMs and SQL instances on VMs**

  ![image](https://github.com/user-attachments/assets/ead498c7-7189-4d83-b8c7-c04a7372158d)

  ![image](https://github.com/user-attachments/assets/89939090-224e-4dbc-8b2e-e2a8c30d2a44)

  ![image](https://github.com/user-attachments/assets/4a0c2c3b-268b-44bc-8698-eefb69fb3642)

  ## **Enable MDC for subscription**

  ![image](https://github.com/user-attachments/assets/ba895236-e2f4-43f2-9bcd-1eed4b4f88e5)

  ![image](https://github.com/user-attachments/assets/016876ba-49e0-4f05-a1a7-ed407570defd)

  ## **Enable MDC for cloud continuous export**

  This will export alerts into log analytics workspace

  ![image](https://github.com/user-attachments/assets/122039f8-780e-4adb-8792-a640ebb44322)

  ![image](https://github.com/user-attachments/assets/b7d023fd-ad76-4d58-993b-15a61b824f87)

</details>

<details><summary>Enable log collections from VMs and NSGs</summary><br>

  Collecting logs from VMs in Azure is different from other resourcesbecause VMs
  require agents to be installed and configured to enable logging and monitoring.

  # **Creating a storage account in Azure**

  ![image](https://github.com/user-attachments/assets/56315839-8967-41ee-8684-4e803e455598)

  ![image](https://github.com/user-attachments/assets/7e377dd6-d41d-4fc8-90af-5883a2281592)

  # **Enabling flow logs for both network security groups (NSGs)**

  ![image](https://github.com/user-attachments/assets/eb981564-66b2-4481-b949-273f9b9122fd)

  ![image](https://github.com/user-attachments/assets/73e62bba-3267-4226-b841-b2e097b383a0)

  ![image](https://github.com/user-attachments/assets/019646d4-17f7-476f-baab-e301702edf40)

  # **Configuring data collection rules within the log analytics workspace**

  The data collection rule will worl in conjunction with defender for cloud and the agents installed on the VMs to specify 
  which logs (system, security, application) from the VMs to forward to the log analytics workspace.

  ![image](https://github.com/user-attachments/assets/26122274-a01a-49b1-a3c9-f364f81199e3)

  ![image](https://github.com/user-attachments/assets/416cecf4-586d-4ae2-8e74-691b13075e24)

  ![image](https://github.com/user-attachments/assets/71ebd780-24fc-48c7-9e5b-a5236320c7f6)

  ![image](https://github.com/user-attachments/assets/33d6150d-ee30-4c94-9624-315f8911a719)

![image](https://github.com/user-attachments/assets/97336654-e87c-4ddd-965e-6af9604d6b84)

![image](https://github.com/user-attachments/assets/bb6b29f2-3a4d-4199-a93b-0c2aae13caa8)

![image](https://github.com/user-attachments/assets/762d5466-576d-4fa2-a224-2b24c50d9a3e)

# **Manually installing the log analytics agent on both windows VM and Linux VM**

  ## **Windows VM**

  I downloaded the agent inside of windows VM andconnected it to the log analytics

  ![image](https://github.com/user-attachments/assets/744cbdea-2e25-4bca-9405-4b312a827331)

  ## **Linux VM**

  To install the agent on Linux VM, I first lgged into the VM using SSH

  ![image](https://github.com/user-attachments/assets/36e658f1-089e-41de-a4e0-0cceb90cf0cc)

  Them I copied the command to install the agent

  ![image](https://github.com/user-attachments/assets/1cc7e8be-8c4f-4434-b1a6-e1349b3f82a8)

  ![image](https://github.com/user-attachments/assets/996a4fa0-c6c5-4ecd-b4f7-972f7cc59865)

  ![image](https://github.com/user-attachments/assets/eff5d73c-0882-42d2-8d7f-048d7c9cf6ed)

# **Query log analytics for logs from VMs and NSGs**

![image](https://github.com/user-attachments/assets/f5db76c8-8b3d-4f0d-b25d-ba27297bbc01)

</details>
<details><summary>Tenant level logging</summary><br>

  # **Create diognostic settings to ingest Azure Entra ID logs**


  ![image](https://github.com/user-attachments/assets/49910441-39f8-4672-b93b-dc6fb4c148bf)

  ![image](https://github.com/user-attachments/assets/b32f133f-afa6-4543-b7f0-e9d38d485779)

  ## **Create a dummy user**

  Creating the user should have generated an audit log. Logging in with the new user should have generated a sign in log

  ![image](https://github.com/user-attachments/assets/deee9bb6-5eb2-4bda-ab7f-5ae67487f183)

  ![image](https://github.com/user-attachments/assets/7b8cd298-29c9-45a1-bda1-d438aefae597)

  ## **Assign dummy_user the role of global administrator.**

  This should generate another audit log.

  ![image](https://github.com/user-attachments/assets/b7344d18-ecd2-4efb-8a1b-f07312b797ab)

  # **Deleting the dummy user**

  ![image](https://github.com/user-attachments/assets/4c1e4898-1c1c-413f-a1df-9ea4ef6bef99)

# **Observe audit logs in log analytics workspace**

![image](https://github.com/user-attachments/assets/4c82308b-beb4-4620-9a2e-46d2a0a4f3a0)

![image](https://github.com/user-attachments/assets/22fdd6eb-a81f-415b-a0f5-8c116921145b)

# **Simulate a brute force attack against Entra ID**

  # **Creating an "attacker" user**

  ![image](https://github.com/user-attachments/assets/5dd279aa-599f-4908-950f-5aa43265e76f)

  After logging in successfully with the attacker user, I logged out and attempted to
  log back in with wrong credentials 10 times

  ![image](https://github.com/user-attachments/assets/458b994e-4a39-48fc-995d-21f72b8d3a50)

  ![image](https://github.com/user-attachments/assets/bb068f1c-7739-40c5-82ff-8c35f078b554)

  # **Checking logs**

  Observing some of the logs related to the brute force attacks (failed logins)

  ![image](https://github.com/user-attachments/assets/05865ca4-51d9-4ec7-bc7c-0da816a69ad5)

  # **Using KQL to further investigate the logs**

  ![image](https://github.com/user-attachments/assets/1473a3fa-8ec7-448d-8ddf-4c36b2f5d07d)

  **Breakdown of the KQL query above**

  - **SigninLogs**: This is the table that contains records of user sign-in activites
  - **| whereResultDescription == "Invalid username or password or invalid on-premises username or password"** :
      - The **where** caluse is used to filter the data to show only rows where specific condition is met.
      - Here, we are looking for sign-in attempts that failed because the username or password was incorrect. So, we are filtering to include only those sign-ins where the ResultDescription says "Invalid username or password or Invalid on-premises username or password."
  - **| extend location = parse_json(LocationDetails)**
      - The **extend** clause is used to create a new column or modigy an existing one.
      - o	Here, we're creating a new column called location by parsing the LocationDetails field. The LocationDetails field contains location data in a format called JSON (JavaScript Object Notation), which is like a structured text that stores data
      ![image](https://github.com/user-attachments/assets/6b113786-f9b5-49ef-b1e7-cd97b46c15f2)

  - **| extend City = location.city, State = location.state, Country = location.countryOrRegion, Latitude = location.geoCoordinates.latitude, Longitude = location.geoCoordinates.longitude**
      - Now, we're breaking down the location data into more specific columns: City, State, Country, Latitude, and Longitude.
      - Each of these new columns extracts a specific piece of information from the location data. For example, City gets the city name, Country gets the country name, and so on.

        ![image](https://github.com/user-attachments/assets/450ec9c5-8523-4c6e-8fc6-20230a3f9f21)

      - **| project TimeGenerated, ResultDescription,   UserPrincipalName, AppDisplayName, IPAddress, IPAddressFromResourceProvider, City, State, Country, Latitude, Longitude:**
          - The **project** clause is used to choose which columns you want to see in the final output.


        

</details>

<details><summary>Subscription Level Logging (Activity Log) </summary><br>
  
  In this lab, I set up activity logs. Activity logs are subscription level logs such as creating resources, deleting resources, changing resources, and changing network security groups.
  
  
  ![image](https://github.com/user-attachments/assets/c7fd4f9e-0c86-4ec4-b3da-86d7adef52fb)

  ![image](https://github.com/user-attachments/assets/4462d18f-2916-483c-a302-b6b6d3560369)

  <br>

  # **Export azure activity logs to log analytics workspace**

  ![image](https://github.com/user-attachments/assets/10deaf06-06ba-421e-8db9-e0ed00d92063)

  ![image](https://github.com/user-attachments/assets/f5bc98bf-27df-4942-860d-523fdeaa5b64)

  **Generate some logs**

  ![image](https://github.com/user-attachments/assets/ecc0127d-5247-4bf8-9081-6d38fc6e78f8)

  # **Create two new resource groups**

  ![image](https://github.com/user-attachments/assets/edaf7c0f-5576-4775-9b75-4c49089a5786)

  ![image](https://github.com/user-attachments/assets/206d5d72-bb8b-4c2b-9f67-8da740aaa8e8)

  **Checking in the monitor to see the logs generated**

  ![image](https://github.com/user-attachments/assets/e636bde1-3a18-4476-a5c4-70804e80f91d)

  <br>
  
  # **After deleting the previously created resource groups, I will query the generated logs to get some information**

  - **Query for the deletion of critical resource group**
      - Here, I am quering the **AzureActivity** table and filtering for only logs associated with **Critical-Infrastructure-** resource group

        ![image](https://github.com/user-attachments/assets/beb30ed3-9d0b-412b-a1a1-77e8d45372bd)


  - **Deletion activities within a certain timestamp**
      - This query will return all the successfully deleted resources within the last 30 minutes

        ![image](https://github.com/user-attachments/assets/2e82462f-f86c-45ac-8c12-481fefd9bcdd)
</details>

<details><summary>Resource Level Logging </summary><br>

  In this lab, I enabled logging for the storage account and forwarding it into the log analytics workspace. I created a key vault (enterprise password manager) and enabled logging for it. 

  # **Configure logging for azure storage account**

  Configure logging for storage account by enabling diagnostic settings for blob storage.

  Blob is the data plane for the storage account. Uploading files, changing the files, and deleting them all actions that will be logged.

  ![image](https://github.com/user-attachments/assets/ce27a1e7-7c16-487e-9520-27d1196fcae3)

  ![image](https://github.com/user-attachments/assets/a5049f65-eca2-43a1-a69f-30f24c999e69)

  ![image](https://github.com/user-attachments/assets/630a72ae-0e9d-47c5-be2b-57151f7d083e)

  # **Configure logging for key vault**

  ## **Create a key vault instance**

  ![image](https://github.com/user-attachments/assets/9b9a30d9-5a69-4e20-a29c-e7fd1a104992)

  ![image](https://github.com/user-attachments/assets/41d2c117-ede2-4083-bb94-3e496f3b4c3b)

  ![image](https://github.com/user-attachments/assets/4719c320-29ef-4750-a07a-aaeb73637b4b)

  ![image](https://github.com/user-attachments/assets/c8970c9f-d6c2-4a93-bf36-14635dbcf35c)

  ![image](https://github.com/user-attachments/assets/bcc47823-fae9-4b8e-b5c2-042b35cb1561)

  ## **Add a secret to the key vault**

  ![image](https://github.com/user-attachments/assets/e2c67082-b83b-4bd2-8350-0f22f829d802)

  ## **Enable diagnostic settings for key vault to send the audit logs**

  ![image](https://github.com/user-attachments/assets/91a24b48-13d8-421d-a62e-c62dffa3d381)

  ![image](https://github.com/user-attachments/assets/33039564-338b-4aad-97d0-8927792502a8)



  # **Generate some logs for storage account**

  ## **Create a new container in the storage account and upload a file.**

  ![image](https://github.com/user-attachments/assets/95fa11af-3003-4802-83ac-5fca4a193ed0)

  ![image](https://github.com/user-attachments/assets/10c74b02-3213-41cb-9080-104357b57668)

  ![image](https://github.com/user-attachments/assets/fce451c0-d7b5-42c2-91df-8c1e29a0ed49)

  ## **Editing the file will create another log**

  ![image](https://github.com/user-attachments/assets/539712c5-94c2-4eb1-af43-4208ac02ec06)

  ![image](https://github.com/user-attachments/assets/717d78d6-b484-4932-aaaa-f339629e2693)

  ## **Deleting the blob file should also generate logs**

  ![image](https://github.com/user-attachments/assets/dec8aba6-7844-452e-bc41-3fc47db250d7)


  # **Analyzing the logs in the log analytics workspace to verify**

  ![image](https://github.com/user-attachments/assets/62901c58-877c-41c1-99d3-5fe54b82ceb6)

  - **Quering logs related to the creation or uploading of blobs (files) within the last 24 hours**

    ![image](https://github.com/user-attachments/assets/f6fc1dfd-dbf8-45f0-9bb1-a2cff6d6cb98)

      - **StorageBlobLogs**: This refers to the table containing logs for operations performed on Azure storage blobs (files)
      - **| where OperationName == “PutBlob”**: **Where** clause filters logs to show only entries with certain criteria. In this case, we are looking for logs where the operation name is PutBlob which refers to the operation of uploading or creating a blob.
      - **| where TimeGenerated >  ago(24h)**:  This further filters the results to include only logs where the operation happened within the last 24 hours.


    - Quering logs related to the deletion of blob files

      ![image](https://github.com/user-attachments/assets/b0368894-5505-4c60-be37-e1562b62bebe)

        - **| Summarize Count = count() by OperationName, CallerIpAddress**: The **summarize** clause is used to group the filtered results and perform aggregations.
In this case, the query counts the number of **DeleteBlob** operations and groups the results by **OperationName** and **CallerIpAddress**. 





  









  


  
</details>

