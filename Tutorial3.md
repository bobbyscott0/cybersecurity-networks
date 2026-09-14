TUTORIAL 3

![Screenshot](Images3/Screenshot%202026-09-09%20154501.png)
: This shows the IPv4 neighbor cache (essentially Windows' ARP table), mapping IP addresses to link-layer MAC addresses for each interface. Most entries are "Permanent" multicast/broadcast addresses (like 224.0.0.x and 255.255.255.255) that don't need MAC resolution, while the useful entries are the "Reachable" gateway (10.233.176.1) with a resolved MAC and a "Stale" entry for 10.233.191.254, meaning that mapping was learned before but hasn't been recently confirmed.
