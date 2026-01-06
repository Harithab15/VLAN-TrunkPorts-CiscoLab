


# VLAN and Trunk Ports Configuration – Cisco Lab (Packet Tracer)

This repository contains a practical Cisco Packet Tracer lab that demonstrates VLAN segmentation and trunking between switches. The goal of the lab is to simulate how inter-VLAN communication is handled in real-world networks using trunk ports and static VLAN assignments.


Designed and tested in **Cisco Packet Tracer v8.x**  
Lab includes `.pkt` topology file and documentation  
Screenshots available under `images/` folder


## Lab Overview

This lab focuses on:

- Creating multiple VLANs on switches
- Assigning access ports to each VLAN
- Configuring trunk ports between switches
- Testing inter-VLAN communication with PCs

You will gain hands-on experience with:
- VLAN configuration commands
- Trunk encapsulation (`dot1q`)
- Interface mode transitions (`access` vs `trunk`)
- Verifying VLANs and trunk links using `show` commands

---

## Lab Topology

![Lab Topology](Lab-Topolgy.png)

- **Switch1** and **Switch2** are connected using a trunk link.
- VLAN 10 and VLAN 20 are created and PCs are assigned accordingly.
- VLANs are manually assigned to switch ports.

---

## Devices Used

| Device       | Purpose               |
|--------------|------------------------|
| 2 x Switches | VLAN config + trunking |
| 4 x PCs      | End devices in VLANs   |

---

##  Lab Setup Steps

### 1. VLAN Creation

On both switches:
 ```bash
Switch(config)# vlan 10
Switch(config-vlan)# name HR

Switch(config)# vlan 20
Switch(config-vlan)# name IT

```
### 2. Access Port Assignment

 ```bash
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
```
### 3. Trunk Port Configuration
Between Switch1 and Switch2:
```bash
Switch(config)# interface fa0/2
Switch(config-if)# switchport trunk encapsulation dot1q
Switch(config-if)# switchport mode trunk
```
### 4. Verification Commands
```bash
Switch# show vlan brief
Switch# show interfaces trunk
```
 ## Testing

Ping between PCs in the same VLAN: Should succeed

Ping between PCs in different VLANs: Should fail (no inter-VLAN routing)

Verify trunk link status

Ensure correct VLAN port assignment

## How to Use
Clone this repo
git clone https://github.com/<your-username>/VLAN-TrunkPorts-CiscoLab.git

Open Trunkports.pkt in Cisco Packet Tracer

Follow the configuration steps above or refer to the article 

Verify and test the configuration using ping and show commands


## Contributing

Pull requests are welcome! If you’d like to contribute enhancements to the topology, feel free to fork and send a PR.

## Tags

#VLAN #CiscoPacketTracer #Trunking #NetworkingLabs #CCNA #GitHubLab #NetworkingFundamentals


