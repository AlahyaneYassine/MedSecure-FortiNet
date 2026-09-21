# VLAN Segmentation

Network segmentation is used to isolate the main functional zones of the healthcare infrastructure.

| VLAN | Network | Purpose |
|---|---|---|
| VLAN 10 | 192.168.10.0/24 | Administration |
| VLAN 20 | 192.168.20.0/24 | Medical Staff |
| VLAN 40 | 192.168.40.0/24 | Servers |

## Security Objective

VLAN segmentation helps limit unnecessary communication between network zones and provides a foundation for implementing access-control policies on the FortiGate firewall.
