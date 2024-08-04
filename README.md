# MICROSOFT-SENTINEL
Understanding Microsoft Sentinel
Microsoft Sentinel is a cloud-based SIEM (security information event management) solution that offers advanced intelligence tools across the organizations to secure the cloud and on-premises resources. The core offering of the Microsoft Sentinel revolves around collecting data at scale while detecting the threat in real-time using artificial intelligence to hunt the suspicious activities, ultimately performing actions to either remediate based on the preconfigured actions or provide a response plan to the security teams in an organization.
While deploying new resources in the cloud, securing the assets is crucial as keeping them highly available for production usage. Whether it's a simple DDoS attack or a complicated privilege escalation attack, Microsoft Sentinel gives you the visibility to detect and respond to the attack before it's too late. Understanding how the SIEM tools work and leveraging them to their maximum be a significant differentiator for your job role and skills. For further reading https://learn.microsoft.com/en-us/azure/sentinel/overview?tabs=azure-portal

In this lab, we will be able to:
- Use Data Connector to collect Windows VM Security Events
- Create Analytics Rule to detect and create incidents based on Security Events
- Investigate incidents in Microsoft Sentinel

In our Microsoft Azure environment, we already have our Virtual Network (HUGO-VNet), Virtual Machine (vm1) created in our resource group (ugochukwu.ejelonu).
![overview](https://github.com/user-attachments/assets/615d4eb0-9ff5-46a5-8f42-dd5550eb4d0e)

I also created another resource group, which contained our Log Analytics workspace and our Sentinel solution.
![overview2](https://github.com/user-attachments/assets/bb48b891-5c83-47fc-840f-d712fef74be1)

In this section, we connected the VM to the Log Analytics. We can see that from the images attached and the next one confirms the VM been connected to the Log Analytics.
![Adding VM to the Log Analytics](https://github.com/user-attachments/assets/3b7b1085-c1f7-4de8-a47c-2d7fd6bc650e)
![VM connection](https://github.com/user-attachments/assets/be15b7ec-3307-42f8-bda3-343267551c72)

## Collecting Datas from events.
In this section of the lab, i was able to set up the Log Analytics to collect syslog logs from the VM since it is now connected.
From the image attached we can see the column for Windows event logs, Windows performance counters, Linux performance counters, Syslogs and IIS logs.
In this lab, Syslog was used to collect data. Collecting the data also supports addition of facility which comes with different severity. *auth* and *syslogs* was the facility used and severity was set to Emergency, Alert & Info.
![syslogs](https://github.com/user-attachments/assets/ca5cf953-fb7a-4599-9f1c-8f939a6cf833)

## SETTING UP SENTINEL
In the section we created Sentinel and added the Log Analytics workspace.
![Sentinel-creation](https://github.com/user-attachments/assets/a8cf12e9-258a-4f98-95b6-7f27bb318bdc)

This next image shows the overview page of our Sentinel solution.
![sentinel-overview](https://github.com/user-attachments/assets/f80bf9b3-ad8c-4e2f-9c5a-3b2aaef37667)

## DATA CONNECTORS
Introduction
Microsoft Sentinel offers multiple data connectors to collect data from multiple sources and improve the ingress capabilities of the SIEM solution. Some of the common options include API-based connection, Diagnostic settings, and Log Analytics agent-based connection.
While working with Azure VM, Sentinel provides agent-based monitoring for real-time log captures and collection to give native end-to-end integration. The agent-based monitoring installs the collection agent on the host, which continues to operate as long as the host is active and sends real-time data to the connected log analytics workspace. For more information https://docs.microsoft.com/en-us/azure/sentinel/connect-data-sources#rest-api-integration 

In this lab step, i created a data collection rule in Sentinel data connector to capture security events from an Azure VM.

In the image below, we already have two (2) data connectors set up.
![data connectors](https://github.com/user-attachments/assets/a6c08101-a81e-4b01-b2d2-fac7da796f1b)
From content hub i was able to add the Windows Security Event.
![content-hub](https://github.com/user-attachments/assets/92ba553a-4705-464c-adf2-a7b45d080a89)

Windows Security Event solution for Microsoft allows you to ingest security events from your Windows machines using the Windows Agent into Microsft Sentinel. Thsi solution includes two (2) data connectors to help ingest the logs.
- Windows Security Event via AMA
- Security Event via Legacy Agent
Microsoft recommends the use of Windows Security Event via AMA, which was used in this lab.
![windows security event](https://github.com/user-attachments/assets/a8784269-6d4e-4f9f-b6da-41f88815d019)
We installed Windows Security Event
![AMA](https://github.com/user-attachments/assets/cd6d55bc-a5b8-4d01-959a-538d1c45ef5f)

![disconnected](https://github.com/user-attachments/assets/1ccfa170-b35c-476d-9aec-de3de5a3bbd3)
The connector is currently disconnected, and no data is available.

Next 
![data collection rule](https://github.com/user-attachments/assets/32d0d727-e484-4eb3-ac92-1d8dd23963c9)

In this lab step, you created a data collection rule in Sentinel data connector to capture security events from an Azure VM.
![CONNECTED](https://github.com/user-attachments/assets/c8a8021f-15af-434f-892c-3a3ee95adac5)

## CREATING SENTINEL ANALYTICS RULE
 
Sentinel threat detection offers security experts and analysts the capability to capture threats based on specific metrics and rules to take actions proactively before the systems are compromised. The attacks can be in any form, including password attack, roles and permissions misusage, database infiltration, DDoS against web servers, or lateral privilege escalation involving multiple compromised resources.
Since identifying and hunting for these kinds of attacks can be cumbersome if done manually, the analytics rule allows you to schedule queries that run on a specific interval and evaluate the environment to match events that are potential for an attack. You can either use Microsoft's provided in-built detection templates or create your own rules based on your business needs.
In this lab step, i will create an Analytic rule for the Sentinel workspace to detect brute-force password attacks and create automatic incidents.
![analytics](https://github.com/user-attachments/assets/f90d140c-de82-4990-9bbe-fd8e87a61b1e)
















