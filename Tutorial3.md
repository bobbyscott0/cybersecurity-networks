TUTORIAL 3

![Screenshot](Images3/Screenshot%202026-09-09%20154501.png)
: This shows the IPv4 neighbor cache (essentially Windows' ARP table), mapping IP addresses to link-layer MAC addresses for each interface. Most entries are "Permanent" multicast/broadcast addresses (like 224.0.0.x and 255.255.255.255) that don't need MAC resolution, while the useful entries are the "Reachable" gateway (10.233.176.1) with a resolved MAC and a "Stale" entry for 10.233.191.254, meaning that mapping was learned before but hasn't been recently confirmed.


![Screenshot](Images3/Screenshot%202026-09-28%20152852.png)


I used diagrams.net to draw a switched LAN network diagram in a star topology. The diagram has three switches, with Switch 3 labeled as the central switch and connected to both Switch 1 and Switch 2. PC1, PC2, and PC3 are connected to Switch 1, and PC4, PC5, PC6, and PC7 are connected to Switch 2. I used the Networking shapes for the PC and switch icons and labeled each device so the layout is easy to follow.
