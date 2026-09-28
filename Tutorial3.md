TUTORIAL 3

![Screenshot](Images3/Screenshot%202026-09-09%20154501.png)
: This shows the IPv4 neighbor cache (essentially Windows' ARP table), mapping IP addresses to link-layer MAC addresses for each interface. Most entries are "Permanent" multicast/broadcast addresses (like 224.0.0.x and 255.255.255.255) that don't need MAC resolution, while the useful entries are the "Reachable" gateway (10.233.176.1) with a resolved MAC and a "Stale" entry for 10.233.191.254, meaning that mapping was learned before but hasn't been recently confirmed.


![Screenshot](Images3/Screenshot%202026-09-28%20152852.png)


I used diagrams.net to draw a switched LAN network diagram in a star topology. The diagram has three switches, with Switch 3 labeled as the central switch and connected to both Switch 1 and Switch 2. PC1, PC2, and PC3 are connected to Switch 1, and PC4, PC5, PC6, and PC7 are connected to Switch 2. I used the Networking shapes for the PC and switch icons and labeled each device so the layout is easy to follow.



LEARNING REFLECTION
The tools we have learned so far are mainly focused on Microsoft PowerShell and how we can use it to understand our computers and the networks they use. With commands like Get-ComputerInfo, we can quickly find out how much memory a machine has, what processor it runs on, and how many logical processors are available. We also looked at the Linux kernel diagram, which showed how an operating system is organized into layers, from the user space interfaces at the top down to the hardware at the bottom. In addition, we used diagrams.net to draw network diagrams, which helped us see how devices like PCs and switches connect to each other in a LAN. This is useful in the real world because you can't protect a system or network you don't understand. Knowing what hardware a computer has, how its resources are being used, and how devices are connected is the first step toward spotting things that don't belong, such as unusual memory usage, unknown devices on a network, or a weak point in how a network is laid out. These skills are the foundation for understanding cybersecurity concepts, since security professionals have to know how a system normally works before they can tell when something is wrong.
