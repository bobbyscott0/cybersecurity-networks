ASSETS

Asset 1: Customer personal details (names, addresses, phone numbers)

Protection: Confidentiality (secondary: integrity)
Reason: Customers' details must not be seen by other customers or outsiders, because leaked data can lead to identity theft and legal trouble. Integrity also matters, since wrong or altered details could cause deliveries or contact to go to the wrong person.

Asset 2: Financial and transaction records

Protection: Integrity
Reason: Records of sales and payments must not be altered without authorization. If someone changed amounts or deleted entries, the business could lose money, and fraud would be hard to detect or prove.

Asset 3: Network infrastructure (router, Wi-Fi, and internet connection)

Protection: Availability
Reason: If the network goes down, staff can't process payments, access the server, or serve customers, so the business loses sales and productivity until it's fixed.

Asset 4: Staff and admin login credentials

Protection: Confidentiality
Reason: If an attacker gets admin passwords, they can access every other asset, change settings, and cover their tracks. Keeping credentials secret protects the whole system.

THREATS

Threat Source 1: Disgruntled employee (insider)

Motivation: wants revenge on the business after being fired, disciplined, or passed over, so they might delete records, change financial data, or leak customer details.
Assets at risk: customer personal details, financial records.

Threat Source 2: Cybercriminal (external attacker)

Motivation: wants financial gain, for example by stealing customer data to sell, stealing payment information, or locking the server with ransomware and demanding payment.
Assets at risk: customer personal details, network and server availability.

Threat Source 3: Competitor

Motivation: wants a business advantage, for example by stealing customer lists, pricing, or plans, or by disrupting the network to hurt sales.
Assets at risk: customer personal details, network avail

CVE

CVE 1: Critical
CVE ID: CVE-2026-19598
Description: The Pods plugin for WordPress allows privilege escalation through an authorization bypass in all versions up to 3.3.9. The cause is that when an access check fails, the code only writes the failure to the PHP error log and returns false instead of stopping the request, so none of the guards work. 
incibe
nist
Date: Published 08/15/2026 
nist
CVSS v3.1: 9.8 Critical, with vector AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H 
githubusercontent
CIA impact: Confidentiality High, Integrity High, Availability High. An attacker who becomes an admin can read, change, or delete everything on the site.
CWE: CWE-863, Incorrect Authorization 
nist
Company: Pods Foundation (the developer is listed as sc0ttkclark) 
githubusercontent
ncsc
Product: Pods – Custom Content Types and Fields is a WordPress plugin used to create custom post types, taxonomies, fields, and settings pages, and it has over 100,000 active installations. 
hol
Simple explanation: The plugin has a gatekeeper that checks whether a visitor is allowed to use admin functions. When the check fails, the code makes a note in a log but keeps going, so the admin action still runs. An unauthenticated attacker can use this to create or overwrite user accounts, including administrators, which means a full site takeover with no password. 
invicti
Detection / mitigation:
Update to a patched version, such as 3.3.9.1 for the current release line. 
intruder
If you can't update right away, disable the plugin, block unauthenticated POST requests to the vulnerable AJAX endpoint at the firewall, and check WordPress for unexpected new accounts. 
invicti
Rotate admin passwords afterwards.


CVE 2: High
CVE ID: CVE-2026-9923
Description: A use-after-free in Skia in Google Chrome versions before 148.0.7778.216 allowed a remote attacker to potentially exploit heap corruption through a crafted HTML page. 
nist
Date: Published 05/28/2026 
nist
CVSS v3.1: 8.8 High, with vector AV:N/AC:L/PR:N/UI:R/S:U/C:H/I:H/A:H 
redhat
CIA impact: Confidentiality High, Integrity High, Availability High. Corrupted memory could let an attacker read data, run their own code, or crash the browser.
CWE: CWE-416, Use After Free 
nist
Company: Google
Product: Google Chrome, a web browser. Skia is the graphics library Chrome uses to draw what you see on screen.
Simple explanation: The program frees a piece of memory but keeps using it afterwards. An attacker can build a web page that puts their own data into that freed memory, so the browser then acts on data the attacker controls. The victim only has to visit the page, which is why User Interaction is "Required."
Detection / mitigation:
Update Chrome to 148.0.7778.216 or later. Check your version in Settings → About Chrome, then restart the browser.
Avoid untrusted sites until you've updated.


CVE 3: Medium
CVE ID: CVE-2026-11176
Description: An inappropriate implementation in the Media component of Google Chrome before 149.0.7827.53 allowed a remote attacker to leak cross-origin data through a crafted HTML page. 
nist
Date: Published 06/04/2026 
nist
CVSS v3.1: 6.5 Medium, with vector AV:N/AC:L/PR:N/UI:R/S:U/C:H/I:N/A:N 
ubuntu
CIA impact: Confidentiality High, Integrity None, Availability None. The attacker can read data but can't change it or break anything.
CWE: CWE-346, Origin Validation Error 
nist
Company: Google
Product: Google Chrome, a web browser. The Media component handles audio and video playback.
Simple explanation: Browsers enforce a rule (the same-origin policy) that stops one website from reading data that belongs to another site you're logged into. A flaw in how Chrome's Media feature checks where a request comes from lets a malicious page get around that rule. It could then read information from another site, such as content from an open webmail tab.
Detection / mitigation:
Update Chrome to 149.0.7827.53 or later.
Keep automatic updates on.
Be careful with unfamiliar links.

TASK 4

Why vendors take time. When a researcher reports a flaw, the vendor first has to confirm it, find the root cause, and build a fix. The fix then has to be tested so it doesn't break other features, and for hardware or firmware (like routers) that is slow. Vendors may also be coordinating with other companies whose products share the same code, or waiting for their regular patch release. Some delay is also self-interested, such as protecting reputation, and I think that part is less justifiable.

What a reasonable time is. There's no single answer, and organizations differ. Google's Project Zero has used a 90-day deadline, the CERT Coordination Center uses 45 days, and HP's Zero Day Initiative uses 120 days. Project Zero also uses a much shorter seven-day deadline for bugs already being exploited in the wild. The trend is toward shorter windows: Project Zero plans to drop from 90 days to 60 days in February and 30 days in January 2028. AI-assisted vulnerability discovery is a reason given for this change, since flaws are now easier to find and exploit. I think around 45 to 90 days is reasonable for most bugs, shorter for critical ones, and much shorter if attackers are already using the flaw. A vendor that is making real progress and communicating should be able to get a short extension.

Task 5 

Purpose. The OWASP Top 10 is an awareness document for developers and web application security, representing broad consensus about the most critical risks to web applications. It isn't a complete list of every possible flaw. It's a ranked starting point based on real data, and the latest edition was announced in November 2025, finalized in January 2026, and is the first update since 2021, drawing on analysis of more than 175,000 CVEs. 
owasp
parasoft

Why it's important. For developers, it gives a short, realistic list of what to avoid, so they can learn secure coding habits without having to know every vulnerability. For security professionals, it gives teams and clients a shared language, helps them prioritize testing and training, and helps explain risk to non-technical managers. The list also shows how threats change. The 2025 edition keeps Broken Access Control at number one, moves Security Misconfiguration from fifth to second, and adds two new categories: Software Supply Chain Failures and Mishandling of Exceptional Conditions. That tells developers that dependencies and error handling matter, not just their own code. 
qualys

It connects to my CVE work in Task 3. The Pods plugin flaw (CVE-2026-19598) was an authorization failure (CWE-863), which falls under Broken Access Control, the top category. Seeing a real critical CVE match the top OWASP risk showed me the list reflects what actually happens. It does have limits, though. The categories are deliberately high-level and meant to raise awareness rather than serve as a testing checklist, so passing "the Top 10" doesn't mean an application is secure. I see it as a foundation to build on, not a finish line. 
