# IP Addressing Plan

| Network | Subnet | Gateway | Purpose |
|---|---|---|---|
| VLAN 10 | 192.168.10.0/24 | 192.168.10.1 | Administration |
| VLAN 20 | 192.168.20.0/24 | 192.168.20.1 | Medical Staff |
| VLAN 40 | 192.168.40.0/24 | 192.168.40.1 | Servers |
| Laboratory LAN | 192.168.50.0/24 | 192.168.50.1 | Remote Laboratory |
| IPsec Transit | 172.16.255.0/30 | — | Site-to-site VPN |
| SSL-VPN Pool | 10.10.10.0/24 | — | Remote Access |
| WAN | 10.0.137.0/24 | 10.0.137.1 | Internet Access |
