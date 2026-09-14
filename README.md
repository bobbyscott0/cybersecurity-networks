# cybersecurity-networks
for IS 353 TUTORIAL 1
![Screenshot](Images3/Screenshot%202026-09-02%20155128.png)
![Screenshot](Images3/Screenshot%202026-09-02%20160430.png)

TUTORIAL 2

![Screenshot](Images3/Screenshot%202026-09-14%20152309.png)
This shows an internet bandwidth test with 46.02 Mbps download and 36.12 Mbps upload speeds, and separate latency (ping) figures for different use cases — 36 ms unloaded, 20 ms for downloads, and 17 ms for uploads (measuring latency under load).
![Screenshot](Images3/Screenshot%202026-09-14%20152409.png)
This is a ping test to the host 10.233.177.131, confirming reachability. The test succeeded (PingSucceeded: True) with a round-trip time of 102 ms, sent from the local Wi-Fi interface's address (10.233.189.213).
![Screenshot](Images3/Screenshot%202026-09-14%20152440.png)
This shows the IP configuration for the active interfaces. The Wi-Fi adapter is connected to a network profile ("HoundNet_Guest 3") with a private IPv4 address (10.233.189.213), a default gateway (10.233.176.1), and several DNS servers configured, while the Bluetooth interface remains disconnected with no IP info.
![Screenshot](Images3/Screenshot%202026-09-14%20152636.png)
This lists the network adapters on the machine, showing their status, MAC address, and link speed. It shows two disabled/not-present Wi-Fi adapters, a disconnected Bluetooth PAN adapter, and the active Wi-Fi adapter running at 400 Mbps link speed with MAC address 58-02-05-F3-1C-A0.
![Screenshot](Images3/Screenshot%202026-09-09%20154501.png)
: This shows the IPv4 neighbor cache (essentially Windows' ARP table), mapping IP addresses to link-layer MAC addresses for each interface. Most entries are "Permanent" multicast/broadcast addresses (like 224.0.0.x and 255.255.255.255) that don't need MAC resolution, while the useful entries are the "Reachable" gateway (10.233.176.1) with a resolved MAC and a "Stale" entry for 10.233.191.254, meaning that mapping was learned before but hasn't been recently confirmed.


