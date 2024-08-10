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

