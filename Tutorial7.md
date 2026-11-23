Cloud concepts. The Azure cloud concepts module explains that cloud computing delivers services such as servers, storage, and networking over the internet on a pay-as-you-go basis. This is a consumption-based model, which means that instead of paying large upfront costs (CapEx) for hardware, organizations pay for what they use as an ongoing expense (OpEx). I found the three service types interesting: IaaS (like a virtual machine, where I manage the OS), PaaS (where the provider manages the platform), and SaaS (ready-to-use software like Microsoft 365).


Shared responsibility. An important point is the shared responsibility model: Microsoft secures the physical datacenters and infrastructure, while the customer is responsible for things like their data, accounts, and access settings. How much falls on the customer depends on whether they use IaaS, PaaS, or SaaS.


Virtual machines and networking. The Windows VM quickstart shows that a VM is created inside a resource group and that network access is controlled by inbound port rules. This connects to what we learned in earlier tutorials, because opening a port like RDP to the internet increases security risk, so it should be 
restricted.


Storage security. The module on securing Azure Storage covers protecting data with encryption, access control, and limiting who can reach a storage account. 
This shows that security needs to be configured deliberately and isn't automatic.


Credentials. The doc also points to Microsoft Applied Skills and the AZ-900 Azure Fundamentals certification. AZ-900 is an entry-level exam, while Applied Skills are shorter practical assessments, which could be useful for building career credentials.
