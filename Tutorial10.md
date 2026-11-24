Selected strategies and how they're applied

1. Patch operating systems (Limit the Extent of Cyber Security Incidents)
Turn on automatic updates for Windows Server 2022 on SRV-01 and for the staff laptops, and check for router firmware updates on the TP-Link router (currently version 1.3.2) once a month. Anything running an unsupported operating system gets replaced. This closes known holes before attackers can use them, like the CVEs we looked at earlier.

2. Multi-factor authentication (Limit the Extent of Cyber Security Incidents)
Require a second step (an authenticator app code) for the Microsoft 365 email accounts, the remote admin login to SRV-01, and the accounting software. The router admin page also gets a long, unique password. If a password is guessed or phished, the attacker still can't log in, which protects the customer and financial data.

3. Restrict administrative privileges (Limit the Extent of Cyber Security Incidents)
Only the part-time IT admin gets an admin account, and that account is used for admin tasks only, not email or browsing. Sales staff get standard accounts that can see customer records but can't install software or change settings. The external bookkeeper gets access to accounting records only. This limits the damage if a staff account is hacked, and it stops a disgruntled employee from deleting records or changing settings.

4. Regular backups (Recover Data and System Availability)
Back up the customer database, financial records, and password data from SRV-01 to NAS-01 every night, plus an encrypted copy to cloud storage. Keep one copy that's disconnected from the network, and test a restore every few months. If ransomware locks the server or the hardware fails, the business can restore its data and keep trading.



Selected controls

1. AC-6: Least Privilege (Family: AC, Access Control)

Why it matters: Each person should have only the access they need for their job. This limits the damage from a hacked account or a disgruntled employee.
How I'd apply it: Sales staff get standard accounts that can view customer records but can't install software or change settings. The external bookkeeper can only open the accounting records. Only the part-time IT admin has admin rights on SRV-01 and the router, and uses a separate admin account for those tasks.

2. IA-2: Identification and Authentication (Organizational Users) (Family: IA, Identification and Authentication)

Why it matters: Every user must prove who they are before accessing systems, so attackers can't just walk in with a guessed or stolen password.
How I'd apply it: Every staff member gets their own login (no shared accounts). Multi-factor authentication (an authenticator app) is required for Microsoft 365 email, remote access to SRV-01, and the accounting software. The router admin page gets a long, unique password in place of the TP-Link default.

3. AT-2: Literacy Training and Awareness (Family: AT, Awareness and Training)

Why it matters: Staff are often the easiest way in. Phishing emails and fake links trick people into handing over passwords or running malware.
How I'd apply it: Run a short security session when staff are hired and a refresher every six months. It covers spotting phishing emails, not reusing passwords, locking laptops, and who to tell if something looks wrong. The sales staff are the main audience since they use email and handle customer data all day.

4. CP-9: System Backup (Family: CP, Contingency Planning)

Why it matters: Ransomware, hardware failure, or accidental deletion can wipe out the business's data. Backups are how it recovers.
How I'd apply it: Back up the customer database, financial records, and password data from SRV-01 to NAS-01 every night, plus an encrypted copy to cloud storage. Keep one copy offline, and test a restore every few months to make sure it actually works.

5. SC-7: Boundary Protection (Family: SC, System and Communications Protection)

Why it matters: The point where the business network meets the internet is the first place attackers probe. Controlling what crosses it blocks many attacks.
How I'd apply it: Keep the router firewall on and turn off remote management and WPS. Put the guest Wi-Fi (TP-Link_Guest_593C) on a separate network that can't reach the server or staff devices. This stops customers or a neighbor on the guest network from reaching SRV-01 or the POS.

6. SI-2: Flaw Remediation (Family: SI, System and Information Integrity)

Why it matters: Attackers often exploit known flaws that already have fixes available, like the CVEs we reviewed earlier. Applying updates quickly closes those doors.
How I'd apply it: Turn on automatic updates for Windows Server 2022 and the laptops, and check monthly for TP-Link router firmware updates (the router currently runs 1.3.2). Critical security patches get installed within days, and unsupported software gets replaced.
