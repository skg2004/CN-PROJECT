# DHCP and DNS Server configuration using Cisco Packet Tracer
## Objective
The primary objective of this project was to configure a DHCP server in Cisco Packet Tracer, allowing network clients to automatically receive IP addresses and necessary network configurations.
## Devices used
- 1 DHCP Server
- 1 DNS Server
- 4 Switches
- 1 Router
- 15 PCs

## Arranging Network Topology
![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/Arranging%20Network%20Topology.png)

## Setting IP Addresses

### DHCP Server (192.168.0.69)

![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/DHCP%20Server%20(192.168.0.69).png)

### Enabling DHCP Service & creating pools

![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/Enabling%20DHCP%20Service%20%26%20creating%20pools.png)

- serverPool - from 192.168.1.0
- Pool-1 - from 192.168.2.0
- Pool-2 - from 192.168.3.0

### DNS Server (192.168.0.2)
![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/DNS%20Server%20(192.168.0.2).png)

## Configuring Router & DHCP Relay
### Router Configuration

#### IP Addresses for each Interface
- G0/0 : 192.168.0.1 (Facing Server side)
- G1/0 : 192.168.1.1
- G2/0 : 192.168.2.1
- G3/0 : 192.168.3.1
> DNS Server Address: 192.168.0.2

### DHCP Relay setup for each Interface
```
Router# conf t
Router(config)# int g0/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g1/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g2/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# int g3/0
Router(config-if)# ip helper-address 192.168.0.69
Router(config-if)# exit
Router(config)# exit
wr
```
## Setting IP addresses to DHCP for each client
![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/Setting%20IP%20addresses%20to%20DHCP%20for%20each%20client.png)

## Overall Topology
![Screenshot](https://github.com/skg2004/CN-PROJECT/blob/5375be3f7412a4df4b0e623804f07ae5aaf0ca9b/CISCO%20PROJECT%20SS/Overall%20Topology.png)

## Conclusion
With the setup of a DHCP and DNS server, IP address management and domain name resolution can be automated, streamlining network operations for dynamic and scalable environments.
