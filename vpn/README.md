# VPN Configuration

The project implements secure connectivity between the clinic and the remote laboratory, as well as secure remote access for authorized medical staff.

## Site-to-Site IPsec VPN

An IPsec VPN tunnel connects the clinic and laboratory sites.

| Site | Transit Interface | IP Address |
|---|---|---|
| Clinic | TRANSIT_IPSEC | 172.16.255.1/30 |
| Laboratory | TRANSIT_IPSEC | 172.16.255.2/30 |

The IPsec tunnel provides secure communication between the clinic server network and the remote laboratory network.

- Clinic server network: `192.168.40.0/24`
- Laboratory network: `192.168.50.0/24`

## SSL-VPN

SSL-VPN provides secure remote access for authorized medical staff.

- VPN address pool: `10.10.10.0/24`
- User group: `GRP_SSLVPN_MEDECINS`

## Validation

The VPN configurations were tested in the PNETLab environment to verify connectivity between the required network segments.
