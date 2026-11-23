Cloud concepts. The Azure cloud concepts module explains that cloud computing delivers services such as servers, storage, and networking over the internet on a pay-as-you-go basis. This is a consumption-based model, which means that instead of paying large upfront costs (CapEx) for hardware, organizations pay for what they use as an ongoing expense (OpEx). I found the three service types interesting: IaaS (like a virtual machine, where I manage the OS), PaaS (where the provider manages the platform), and SaaS (ready-to-use software like Microsoft 365).


Shared responsibility. An important point is the shared responsibility model: Microsoft secures the physical datacenters and infrastructure, while the customer is responsible for things like their data, accounts, and access settings. How much falls on the customer depends on whether they use IaaS, PaaS, or SaaS.


Virtual machines and networking. The Windows VM quickstart shows that a VM is created inside a resource group and that network access is controlled by inbound port rules. This connects to what we learned in earlier tutorials, because opening a port like RDP to the internet increases security risk, so it should be 
restricted.


Storage security. The module on securing Azure Storage covers protecting data with encryption, access control, and limiting who can reach a storage account. 
This shows that security needs to be configured deliberately and isn't automatic.


Credentials. The doc also points to Microsoft Applied Skills and the AZ-900 Azure Fundamentals certification. AZ-900 is an entry-level exam, while Applied Skills are shorter practical assessments, which could be useful for building career credentials.


![Azure portal screenshot](Images3/Screenshot%202026-11-23%20124642.png)


This is one of the certifications listed on the Azure student learning platform that I found really interesting. This is a certification I would be interested in taking because it is relevant to my major and is going to be pivotal in the new age of business.



![wireshark portal screenshot](Images3/Screenshot%202026-11-23%20130056.png)



First SYN
Packet number: 2117
Source IP / destination IP: 192.168.1.213 → 192.168.1.1
Ports: source 56142, destination 53 (DNS)
Sequence number (raw): 177840813. I read it from the hex pane: the four bytes 0a 99 a2 ad right after the ports (db 4e 00 35) are the sequence number. The Seq=0 in the Info column is only the relative number.
SYN-ACK response

The screenshot shows only SYNs, so I can't read the actual packet number or server numbers. This is what you'd expect:

Packet number: the packet right after the SYN in this stream, from 192.168.1.1 port 53 back to 192.168.1.213 port 56142. It isn't visible here.
Flags: SYN and ACK
Raw numbers: the server's sequence number is its own random starting value, which I can't see here. The acknowledgment number returned will be 177840814.
Why 177840814? The server acknowledges the client's sequence number plus 1. A SYN uses up one sequence number even though it carries no data, so the ack means "I got your SYN, and the next byte I expect is 177840813 + 1."
Final ACK
Packet number: the third packet in the stream, from 192.168.1.213 back to the server. It isn't visible here.
Flags: ACK only
Acknowledgment number (raw): the server's sequence number from Q7, plus 1.
First data packet
This is the first packet in the stream with TCP Segment Len above 0, which would be the client's DNS query. Its flags are typically PSH, ACK. PSH (Push) tells the receiver to hand the data to the application immediately instead of buffering it. ACK means the acknowledgment-number field is valid and confirms the data received so far. Click the packet and expand the TCP section to confirm the exact flags.


---
[⬅ Back to main README](README.md)
