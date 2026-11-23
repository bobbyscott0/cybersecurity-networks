![Wi-Fi details from netsh wlan show interfaces](https://raw.githubusercontent.com/bobbyscott0/cybersecurity-networks/main/Images3/Screenshot%202026-11-23%20122323.png)


SSID: Fios-v4DX8

BSSID: b8:f8:53:30:30:0b (shown as "AP BSSID")

Frequency band: 5 GHz

Channel: 48

Data rate: Receive 1201 Mbps, Transmit 720.5 Mbps

![TP-Link router settings overview](Images3/Screenshot%202026-11-23%20123040.png)
![TP-Link_router_settings_overview](Images3/Screenshot%202026-11-23%20123056.png)
![Tp-Link_wifi_settings_overview](Images3/Screenshot%202026-11-23%20123221.png)


When designing a Wi-Fi network, I would change the default SSID (TP-Link_593D) to a unique name that doesn't reveal the router brand, since default names make it easier for attackers to identify the device. I would also set the wireless mode from 802.11b/g/n mixed to a newer standard like 802.11n or ax, which gives faster speeds and drops support for outdated, slower devices. The channel is currently set to Auto (channel 6), which is acceptable on 2.4 GHz, but I would consider fixing it to channel 1, 6, or 11 if neighboring networks cause interference. I would turn on the guest network, which is currently off, so visitors and smart devices stay separate from my main devices, and keep "Allow guests to see each other" off to isolate them. Finally, I would use WPA2 or WPA3 security with a long, random password and change the default admin password, because these settings protect the network from unauthorized access.


---
[⬅ Back to main README](README.md)
