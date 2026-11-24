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





1. Data assets
ID	Asset	Location	Owner	Classification (value / access)	Key protections	Important protections
D1	Customer personal details (names, addresses, phone, email)	SRV-01 database	Manager	Confidential (high value, need-to-know staff only)	C: High, I: Medium, A: Medium	Encryption at rest, role-based access, access logging
D2	Financial and transaction records	SRV-01 / accounting software	Manager	Confidential (high value, finance staff only)	I: High, C: High, A: Medium	Restrict write access, audit trail, daily backups
D3	Admin and staff login credentials (password hashes)	SRV-01 / router	IT admin	Restricted (very high value, admin only)	C: High, I: High	Strong password policy, MFA, hashed storage
D4	Staff HR records (contracts, payroll)	SRV-01 / HR folder	Manager	Confidential (privacy law applies)	C: High, I: Medium	Access limited to manager, encrypted storage
D5	Backup copies of all data	NAS-01 and offsite cloud	IT admin	Confidential (contains all of the above)	A: High, C: High	Encrypted backups, tested restores, offline copy
D6	System, security, and CCTV logs	SRV-01 / NVR-01	IT admin	Internal (staff and admin only)	I: High, A: Medium	Write-protect logs, regular review, retention policy
D7	Product list, prices, and website content	Website and SRV-01	Manager	Public (low value, open access)	I: Medium, C: Low	Change control so content can't be defaced or altered
2. Hardware assets
ID	Asset	Make / model	Serial no.	MAC address	Location	Owner
H1	Main server (SRV-01)	Dell PowerEdge T150	7XK92M3	A4-BB-6D-12-8C-01	Server cabinet	IT admin
H2	Wi-Fi router	TP-Link Archer C6	2284A0071536	C4-E9-83-EF-59-3C	Back office	IT admin
H3	Network switch	TP-Link TL-SG108	22C1B0045218	98-DA-C4-33-7A-10	Server cabinet	IT admin
H4	Point-of-sale terminal	Generic POS tablet	POS-2026-0041	3C-6A-A7-5B-02-9E	Front counter	Manager
H5	Staff laptop (x2)	Lenovo ThinkPad E14	PF3KQ81X / PF3KQ82A	58-02-05-F3-1C-A0 / 58-02-05-F3-1C-B4	Office	Staff
H6	Backup NAS (NAS-01)	Synology DS223	2210SBN4Q7600	00-11-32-9F-44-D2	Server cabinet	IT admin
H7	CCTV recorder and cameras (NVR-01)	Hikvision DS-7604	DS7604NI-2026-77	BC-AD-28-61-0F-33	Back office	Manager
H8	UPS (battery backup)	APC Back-UPS 1500	3B2112X09876	N/A	Server cabinet	IT admin
3. Software assets
ID	Asset	Version	Purpose	Host	Licence / vendor
S1	Server operating system	Windows Server 2022	Runs the server	H1	Microsoft, volume licence
S2	Customer database	MySQL 8.0	Stores customer and order data (D1, D2)	H1	Open source
S3	POS application	v4.2.1	Processes sales	H4	Vendor subscription
S4	Accounting software	v2026.1	Manages financial records (D2)	H1	Annual licence
S5	Backup software	v7.3	Backs up D1–D4 to NAS and cloud	H6	Vendor licence
S6	Antivirus / endpoint protection	v26.2	Detects malware	H1, H5	Annual subscription
S7	Router firmware	1.3.2 Build 20260301	Runs the router and Wi-Fi	H2	TP-Link
S8	Cloud office and email suite	Microsoft 365 Business	Email and documents	Cloud	Microsoft subscription
4. Network assets
ID	Asset	Identifying details	Purpose	Owner
N1	Main Wi-Fi network	SSID: TP-Link_593D, 2.4 GHz, channel 6, WPA2-Personal	Staff and POS connectivity	IT admin
N2	Guest Wi-Fi network	SSID: TP-Link_Guest_593C, isolated from LAN	Customer and visitor internet	IT admin
N3	Local network (LAN)	192.168.0.0/24, gateway 192.168.0.1, DHCP on	Connects all devices	IT admin
N4	Internet connection (WAN)	ISP fibre, public IP 203.0.113.45 (example), dynamic	Internet and cloud access	Manager
N5	Router admin interface	http://192.168.0.1, admin account	Manages network settings	IT admin
N6	DNS and DHCP services	Provided by router at 192.168.0.1	Name resolution and addressing	IT admin
5. People assets
ID	Role	Employee / contractor ID	Access level	Linked assets
P1	Business owner / manager	EMP-001	Full (admin and finance)	D1–D7, H1–H8
P2	IT administrator (part-time)	EMP-002	Administrator on server and router	D3, D5, H1, H2, S1–S7
P3	Sales staff (x2)	EMP-003, EMP-004	Standard user, POS and customer records	D1, H4, H5, S3
P4	Bookkeeper (external)	CON-101	Read and write on accounting only	D2, S4
P5	External IT support vendor	CON-102	Remote access when requested	H2, S7
P6	Cleaning contractor	CON-103	Physical access after hours	F1, F2
6. Facilities (physical) assets
ID	Asset	Identifying details	Protection in place	Owner
F1	Shop premises	Unit 4, 12 Example Street (fake address)	Lock, alarm, CCTV	Manager
F2	Back office	Rear of F1, door lock	Keyed lock, restricted keys	Manager
F3	Server cabinet	Locked rack in back office, key ID K-07	Lock, ventilation	IT admin
F4	Power supply	Mains plus UPS (H8)	Surge protection, battery backup	IT admin
F5	Safe	Fire-rated safe, ID SAFE-01	Combination lock	Manager
F6	Fire and alarm system	Smoke detectors, alarm panel AP-01	Monitored alarm	Manager








---
[⬅ Back to main README](README.md)
