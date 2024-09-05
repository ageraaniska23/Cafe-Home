# Cafe-Home
OSPF, ACL, DHCP, VTP, DNS Server, Web Server
![image](https://github.com/user-attachments/assets/3cda4298-6b90-4cb1-80e9-0411087015ef)

# Cisco Routing Configuration - VLAN & Network Setup

This repository contains the configuration details for a Cisco network setup that includes VLANs, DHCP, default gateways, and routers. The setup allows communication between different VLANs and servers, including web and DNS servers.

## Network Overview

### VLAN Configuration

| VLAN  | Network         | Default Gateway  |
|-------|-----------------|------------------|
| 10    | 192.168.10.0/24 | 192.168.10.1     |
| 20    | 192.168.20.0/24 | 192.168.20.1     |

### Router Configuration

| Router    | Interface   | IP Address         | Description             |
|-----------|-------------|--------------------|-------------------------|
| Router 2  | G1/0.10        | 192.168.10.1/24    | Default Gateway for VLAN 10 |
| Router 2  | G1/0.20        | 192.168.20.1/24    | Default Gateway for VLAN 20 |
| Router 2  | S0/0        | 192.168.100.1/24   | Connection to Router 3  |
| Router 3  | S0/0        | 192.168.100.2/24   | Connection to Router 2  |
| Router 3  | G1/0        | 10.10.10.11/24     | Connection to Server Network |

### Server Configuration

| Server     | IP Address      | Description       |
|------------|-----------------|-------------------|
| Web Server | 10.10.10.1/24   | Web Server        |
| DNS Server | 10.10.10.2/24   | DNS Server        |

### Additional Information

- **DHCP** is used for IP address allocation within the VLANs.
- **Router 2** serves as the default gateway for both VLAN 10 and VLAN 20.
- **Router 3** is connected to both Router 2 and the server network.
