
# FortiGate Configuration

The FortiGate infrastructure provides firewalling, network segmentation and secure access control for the healthcare environment.

## Network Segmentation

The clinic infrastructure is divided into dedicated network segments:

- **VLAN 10 — Administration:** `192.168.10.0/24`
- **VLAN 20 — Medical Staff:** `192.168.20.0/24`
- **VLAN 40 — Servers:** `192.168.40.0/24`

The segmentation helps isolate different types of traffic and limits unnecessary communication between network zones.

## Security Functions

The FortiGate devices provide:

- Firewall policies
- VLAN segmentation
- Network address translation
- Inter-site IPsec connectivity
- SSL-VPN remote access
- Access control between network segments

## Deployment

The FortiGate devices were deployed in a virtualized PNETLab environment using VMware.
