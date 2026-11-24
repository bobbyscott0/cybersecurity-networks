Selected strategies and how they're applied

1. Patch operating systems (Limit the Extent of Cyber Security Incidents)
Turn on automatic updates for Windows Server 2022 on SRV-01 and for the staff laptops, and check for router firmware updates on the TP-Link router (currently version 1.3.2) once a month. Anything running an unsupported operating system gets replaced. This closes known holes before attackers can use them, like the CVEs we looked at earlier.

2. Multi-factor authentication (Limit the Extent of Cyber Security Incidents)
Require a second step (an authenticator app code) for the Microsoft 365 email accounts, the remote admin login to SRV-01, and the accounting software. The router admin page also gets a long, unique password. If a password is guessed or phished, the attacker still can't log in, which protects the customer and financial data.

3. Restrict administrative privileges (Limit the Extent of Cyber Security Incidents)
Only the part-time IT admin gets an admin account, and that account is used for admin tasks only, not email or browsing. Sales staff get standard accounts that can see customer records but can't install software or change settings. The external bookkeeper gets access to accounting records only. This limits the damage if a staff account is hacked, and it stops a disgruntled employee from deleting records or changing settings.

4. Regular backups (Recover Data and System Availability)
Back up the customer database, financial records, and password data from SRV-01 to NAS-01 every night, plus an encrypted copy to cloud storage. Keep one copy that's disconnected from the network, and test a restore every few months. If ransomware locks the server or the hardware fails, the business can restore its data and keep trading.
