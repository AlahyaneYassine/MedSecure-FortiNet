# FGT_LABO

## Overview

`FGT_LABO` is the FortiGate protecting the remote laboratory environment of the MediClinic infrastructure.

It provides network protection and secure connectivity with the main clinic through a site-to-site IPsec VPN.

## Role in the Architecture

The laboratory FortiGate controls traffic between the remote laboratory network and the IPsec connection to the clinic.

Main functions:

* Remote network protection
* Site-to-site IPsec VPN
* Firewall traffic control
* Network routing
* Security logging

## Network Interfaces

| Interface | Role           | Network           |
| --------- | -------------- | ----------------- |
| `port2`   | Laboratory LAN | `192.168.50.0/24` |
| `port3`   | IPsec transit  | `172.16.255.0/30` |

### Laboratory LAN

```text
Network: 192.168.50.0/24
Gateway: 192.168.50.1
```

### IPsec Transit

```text
FGT_LABO: 172.16.255.2/30
FGT_CLINIQUE: 172.16.255.1/30
```

## Site-to-Site IPsec

`FGT_LABO` establishes a site-to-site IPsec VPN with `FGT_CLINIQUE`.

The protected networks are:

```text
Clinic:
192.168.40.0/24

Laboratory:
192.168.50.0/24
```

The VPN enables controlled communication between the remote laboratory and the clinic server infrastructure.

## Traffic Control

Firewall policies control communication between the laboratory network and the IPsec VPN.

The objective is to allow only the traffic required by the defined architecture while preventing unnecessary access to other network zones.

## Validation

The IPsec connection was validated through:

* IPsec tunnel status verification
* Routing verification
* Connectivity tests between the protected networks
* Ping tests between the clinic and laboratory environments

## Security Note

This repository intentionally excludes sensitive configuration information such as:

* Administrator passwords
* VPN pre-shared keys
* Private keys
* Certificates containing sensitive material
* API tokens
* License files
* Confidential information

Only sanitized architectural and configuration documentation is provided.

