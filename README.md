# Unifi Configuration


Placeholder for all configuration on Unifi for documentation purposes.

## Sections
1. [IPTV](https://github.com/dP210/Unifi/edit/main/README.md#iptv)
2. [Zero-trust DNS (DoH)](https://github.com/dP210/Unifi/edit/main/README.md#zero-trust-dns-doh)


### IPTV
The IGMP proxy needs to be configured such that it routes both IPTV traffic and Internet traffic correctly to devices on the LAN. 

Bell uses a VLAN (36) for IPTV traffic which I have mapped to the IPTV LAN (172.90.100.0/29) for use within the home. The IPTV LAN is isolated to just the Family Room switch to prevent other traffic that may not be firewalled to penetrate across the network.

### Network topology

        Fiber
          |
    +-----------+
    | Bell FTTH |
    +-----------+
          |
      VLAN36 - IPTV
      VLAN35 - Internet
          |
      +--------+
      | Router |  - Ubiquiti UniFi device
      +--------+
          |
         LAN
          |
      +-------------+
      | Core Switch |  - Ubiquiti UniFi Switch (Optional)
      +-------------+
       |            | 
       |            |+-------------+ 
       +-------------+             |  
       | Family Room |             |   
       |  Switch     |             |
       +-------------+             |  
       +--------------+       +---------+      
       |   IPTV STB   |       | WiFi AP |      
       |   VLAN 100   |       |         |
       +--------------+       +---------+      
       - Bel IPTV
       - Web Apps 
       ...

### Network Configuration
![image](https://github.com/user-attachments/assets/b261bcde-57a1-4e9e-add2-b9d219f4f2d5)
Traffic routing from the WAN to the LAN need to be tagged as VLAN 35/36. 

### IPTV VLAN (100) Configuration


## Zero-trust DNS (DoH)
