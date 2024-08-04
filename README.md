# MICROSOFT-SENTINEL
Understanding Microsoft Sentinel
Microsoft Sentinel is a cloud-based SIEM (security information event management) solution that offers advanced intelligence tools across the organizations to secure the cloud and on-premises resources. The core offering of the Microsoft Sentinel revolves around collecting data at scale while detecting the threat in real-time using artificial intelligence to hunt the suspicious activities, ultimately performing actions to either remediate based on the preconfigured actions or provide a response plan to the security teams in an organization.
While deploying new resources in the cloud, securing the assets is crucial as keeping them highly available for production usage. Whether it's a simple DDoS attack or a complicated privilege escalation attack, Microsoft Sentinel gives you the visibility to detect and respond to the attack before it's too late. Understanding how the SIEM tools work and leveraging them to their maximum be a significant differentiator for your job role and skills.
In this hands-on lab, you will understand how to identify, capture and generate incidents for security events and potential attacks using Microsoft Sentinel.

Upon completion of this lab, you will be able to:
- Use Data Connector to collect Windows VM Security Events
- Create Analytics Rule to detect and create incidents based on Security Events
- Investigate incidents in Microsoft Sentinel

In our Microsoft Azure environment, we already have our Virtual Network (HUGO-VNet), Virtual Machine (vm1) created in our resource group.
![overview](https://github.com/user-attachments/assets/615d4eb0-9ff5-46a5-8f42-dd5550eb4d0e)

I also created another resource group, which contained our Log Analytics workspace and our Sentinel solution.
![overview2](https://github.com/user-attachments/assets/bb48b891-5c83-47fc-840f-d712fef74be1)







