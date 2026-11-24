Security Objectives

Protect

Objective 1

Function: Protect (PR)
Category: Identity Management, Authentication, and Access Control (PR.AA)
Sub-category: PR.AA-03: Users, services, and hardware are authenticated
Why it's important: Staff, devices, and the admin panel all need to prove who they are before getting access to the server, customer records, and Wi-Fi. Without strong authentication, anyone who reaches the network can use it.
Attack/vulnerability mitigated: Unauthorized access through default or weak passwords, such as a neighbor joining the Wi-Fi to get free internet or an attacker logging into the router using its default admin password. It also reduces the success of password guessing and credential stuffing. Strong Wi-Fi passwords (WPA2/WPA3), changed admin credentials, and multi-factor authentication on key accounts address this.

Objective 2

Function: Protect (PR)
Category: Data Security (PR.DS)
Sub-category: PR.DS-01: The confidentiality, integrity, and availability of data-at-rest are protected
Why it's important: The most valuable assets are stored on the local server: customer personal details and financial records. Protecting this stored data keeps customers' details private and stops records being quietly altered.
Attack/vulnerability mitigated: Data theft after a breach or physical theft of the server or a drive. If the data is encrypted and access-controlled, a cybercriminal or insider who copies it gets unreadable files. Integrity protections (such as restricted write access and checksums) also help prevent tampering with financial records.
Detect

Objective 3

Function: Detect (DE)
Category: Continuous Monitoring (DE.CM)
Sub-category: DE.CM-01: Networks and network services are monitored to find potentially adverse events
Why it's important: Prevention can fail, so the business needs to notice suspicious network activity early. Monitoring shows which devices are connected and what traffic is leaving the network.
Attack/vulnerability mitigated: Unknown devices on the Wi-Fi (like the neighbor), port scanning and brute-force login attempts against the router or server, and large unusual data transfers that suggest a cybercriminal is stealing customer data. Router logs, connected-device alerts, and a basic intrusion detection tool support this.

Objective 4

Function: Detect (DE)
Category: Adverse Event Analysis (DE.AE)
Sub-category: DE.AE-02: Potentially adverse events are analyzed to better understand associated activities
Why it's important: Collecting alerts and logs isn't enough unless someone reviews them to work out whether an event is a real attack or normal activity. This stops real incidents being ignored among false alarms.
Attack/vulnerability mitigated: Insider threats and account takeover. For example, reviewing logs could reveal a disgruntled employee downloading customer records late at night, or a run of failed logins followed by a successful one, which suggests someone guessed a password. Spotting this early limits the damage.


ASSET MANAGMENT

1. Data assets

Customer personal details (on the server, SRV-01): Confidential. Protect confidentiality most, then integrity.
Financial and transaction records (on the server): Confidential. Protect integrity most, so nobody can alter them, plus confidentiality.
Admin and staff passwords (server and router): Restricted, since only admins should see them. Protect confidentiality and integrity.
Backups of all data (NAS-01 and cloud): Confidential, because they contain everything else. Protect availability most, plus confidentiality.
Product list and website content: Public. Protect integrity so the site can't be defaced.

2. Hardware assets

Server (SRV-01): Dell PowerEdge T150, serial 7XK92M3, MAC A4-BB-6D-12-8C-01
Wi-Fi router: TP-Link Archer C6, serial 2284A0071536, MAC C4-E9-83-EF-59-3C
Staff laptops (x2): Lenovo ThinkPad E14, serials PF3KQ81X and PF3KQ82A
Backup NAS (NAS-01): Synology DS223, serial 2210SBN4Q7600

3. Software assets

Server operating system: Windows Server 2022
Customer database: MySQL 8.0
Accounting software: v2026.1
Router firmware: TP-Link version 1.3.2

4. Network assets

Main Wi-Fi: SSID TP-Link_593D, 2.4 GHz, channel 6, WPA2-Personal
Guest Wi-Fi: SSID TP-Link_Guest_593C, kept separate from the main network
Local network: 192.168.0.0/24, router at 192.168.0.1
Internet connection: ISP fibre line

5. People assets

Business owner / manager: full access to everything
IT administrator (part-time): admin access to the server and router
Sales staff (x2): standard access to customer records and the sales system
External bookkeeper: access to accounting records only

6. Facilities assets

Shop premises: lock, alarm, and CCTV
Back office: keyed door, restricted keys
Server cabinet: locked, with a backup battery (UPS) for power cuts











---
[⬅ Back to main README](README.md)
