# IP Addressing Plan

## Overview

This document describes the IP addressing plan used in the MedSecure-FortiNet laboratory environment.

The addressing scheme separates the different security zones and provides dedicated networks for internal services, the remote laboratory and VPN connectivity.

## Addressing Plan

| Zone           | Network           | Gateway / Address      | Purpose                          |
| -------------- | ----------------- | ---------------------- | -------------------------------- |
| VLAN 10        | `192.168.10.0/24` | `192.168.10.1`         | Administration                   |
| VLAN 20        | `192.168.20.0/24` | `192.168.20.1`         | Medical Staff                    |
| VLAN 40        | `192.168.40.0/24` | `192.168.40.1`         | Servers                          |
| Laboratory LAN | `192.168.50.0/24` | `192.168.50.1`         | Remote Laboratory                |
| IPsec Transit  | `172.16.255.0/30` | See below              | FortiGate IPsec transit          |
| SSL-VPN Pool   | `10.10.10.0/24`   | VPN-assigned addresses | Remote Medical Staff             |
| WAN            | `10.0.137.0/24`   | `10.0.137.1`           | Internet / External Connectivity |

## Clinic Networks

### VLAN 10 — Administration

```text id="h1v2a7"
Network: 192.168.10.0/24
Gateway: 192.168.10.1
```

Used for administrative users and related infrastructure traffic.

### VLAN 20 — Medical Staff

```text id="m4m7k2"
Network: 192.168.20.0/24
Gateway: 192.168.20.1
```

Used for medical staff devices and associated network access.

### VLAN 40 — Servers

```text id="9x7n2p"
Network: 192.168.40.0/24
Gateway: 192.168.40.1
```

Used for protected server resources within the clinic.

## Remote Laboratory

```text id="f6z8r3"
Network: 192.168.50.0/24
Gateway: 192.168.50.1
```

This network represents the LAN of the remote laboratory connected through the site-to-site IPsec VPN.

## IPsec Transit Network

The FortiGate devices use a dedicated point-to-point transit network for the VPN connectivity.

| Device       | Address           |
| ------------ | ----------------- |
| FGT_CLINIQUE | `172.16.255.1/30` |
| FGT_LABO     | `172.16.255.2/30` |

## SSL-VPN Address Pool

```text id="q8x2m5"
Pool: 10.10.10.0/24
```

This address pool is used for authenticated SSL-VPN users.

## WAN Network

```text id="z5j3k1"
Network: 10.0.137.0/24
Gateway: 10.0.137.1
FGT_CLINIQUE: 10.0.137.10
```

This network provides external connectivity to the clinic FortiGate in the virtualized laboratory environment.

## Addressing Principles

The addressing plan follows these principles:

* Dedicated subnet for each security zone
* Clear separation between users and servers
* Dedicated transit network for VPN connectivity
* Dedicated address pool for remote VPN users
* Consistent addressing between the clinic and remote laboratory

## Security Note

The addresses documented here belong to the isolated virtual laboratory environment. No production network addresses or real patient information are included.
