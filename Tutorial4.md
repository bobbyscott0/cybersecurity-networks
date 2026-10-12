![Routing table screenshot](Images3/Screenshot%202026-10-12%20151015.png)


The screenshot shows the output of Get-NetRoute, where each row is one route that tells Windows where to send traffic. The DestinationPrefix column is the network the route applies to, and NextHop is where packets for that network are sent next; a NextHop of 0.0.0.0 (or :: for IPv6) means the destination is directly connected or handled locally, while 10.233.176.1 on the 0.0.0.0/0 row is my default gateway, the route used for any traffic that doesn't match a more specific entry. ifIndex identifies which network interface the route uses, and RouteMetric and ifMetric are priority values, with lower numbers preferred when multiple routes match. Other notable entries include 127.0.0.0/8 (loopback, my own machine), 224.0.0.0/4 (multicast), 255.255.255.255/32 (broadcast), 10.233.176.0/20 (my local subnet), and fe80:: (IPv6 link-local addresses).


![Traceroute screenshot 1](Images3/Screenshot%202026-10-12%20152004.png)

![Traceroute screenshot 2](Images3/Screenshot%202026-10-12%20152215.png)


I traced the route to www.ox.ac.uk, which took 13 hops and reached the destination with a round-trip time of about 6 to 20 ms. Hops 1 to 3 were private addresses (10.x.x.x) inside my local and access network, hops 4 to 6 belonged to Zayo, a large backbone provider, and the final hops (11 to 13) entered Cloudflare's network, which the trace revealed by resolving the address to www.ox.ac.uk.cdn.cloudflare.net. The hostname bwi9 in hops 4 and 5 is the airport code for Baltimore, and iad93 in hop 6 points to the Ashburn, Virginia area, a major internet exchange and data center hub, so the traffic stayed on the US East Coast. I expected a large delay jump for an overseas crossing, but Oxford's website uses Cloudflare's content delivery network, so I was connected to a nearby Cloudflare server instead of one in the UK, which explains the low total delay. The providers involved were my local access network, Zayo as the transit provider, and Cloudflare, and the hops that timed out (7 to 9) are routers that simply don't reply to probes. Delay is normally affected by distance (a true trans-Atlantic path would add roughly 70 to 100 ms), the number of hops, congestion, and routing choices, while communication inside a single local network usually takes only 1 to 3 hops and a few milliseconds because there is little distance, few routers, and little congestion.


![IP screenshot 1](Images3/Screenshot%202026-10-12%20153106.png)


It guesses my location exactly!
