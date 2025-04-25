# Unifi Configuration


Placeholder for all configuration on Unifi for documentation purposes.

## Sections
1. [IPTV IGMP Proxy]([url](https://github.com/dP210/Unifi/edit/main/README.md#zero-trust-dns-doh))
2. [Zero-trust DNS (DoH)](https://github.com/dP210/Unifi/edit/main/README.md#zero-trust-dns-doh)


## IPTV IGMP
The IGMP proxy needs to be configured such that it routes both IPTV traffic and Internet traffic correctly to devices on the LAN. 

Bell uses a VLAN (36) for IPTV traffic which I have mapped to the IPTV LAN (172.90.100.0/29) for use within the home. The IPTV LAN is isolated to just the Family Room 

## Network topology

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
       |         | |
       |         | +-----------------------------+
+-------------+
| Family Room |
|  Switch     |                            |
+-------------+       |  +-----------------+              |
       |                    |              |
+--------------+       +---------+      +-----+
| IPTV STB     |       | WiFi AP |      | ... |
+--------------+       +---------+      +-----+
  - Bel IPTV
  - Web Apps 
...
## Zero-trust DNS (DoH)
