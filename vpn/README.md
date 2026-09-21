# VPN Architecture

## Overview

The MedSecure-FortiNet infrastructure uses two VPN technologies to secure communications:

* **Site-to-site IPsec VPN** for communication between the clinic and the remote laboratory
* **SSL-VPN** for secure remote access by authorized medical staff

Both mechanisms are implemented through FortiGate.

## Site-to-Site IPsec VPN

The IPsec VPN securely connects the MediClinic infrastructure with the remote laboratory.

### Architecture

```text
MediClinic
192.168.40.0/24
      |
      |
FGT_CLINIQUE
172.16.255.1/30
      |
      |  IPsec VPN
      |
FGT_LABO
172.16.255.2/30
      |
      |
Laboratory
192.168.50.0/24
```

### Protected Networks

| Site       | Network           | Purpose           |
| ---------- | ----------------- | ----------------- |
| Clinic     | `192.168.40.0/24` | Server network    |
| Laboratory | `192.168.50.0/24` | Remote laboratory |

### IPsec Transit

| Device       | Address           |
| ------------ | ----------------- |
| FGT_CLINIQUE | `172.16.255.1/30` |
| FGT_LABO     | `172.16.255.2/30` |

The tunnel was validated through connectivity tests between the protected networks.

## SSL-VPN

SSL-VPN provides secure remote access for authorized medical staff.

### Configuration

```text
User group: GRP_SSLVPN_MEDECINS
VPN address pool: 10.10.10.0/24
```

The SSL-VPN connection provides controlled access to the resources authorized by the FortiGate firewall policies.

### Remote Access Flow

```text
Medical Staff
      |
      | HTTPS / SSL-VPN
      |
FortiGate
      |
      | Authentication
      |
VPN Address Pool
10.10.10.0/24
      |
      |
Authorized Internal Resources
```

## Security Controls

VPN access is controlled through:

* User authentication
* Dedicated VPN address pools
* Firewall policies
* Network segmentation
* Restricted access to authorized resources
* Security logging

## Validation

The VPN mechanisms were validated through:

* IPsec tunnel status verification
* Connectivity tests between protected networks
* SSL-VPN configuration verification
* SSL-VPN address pool verification
* Access control testing
* FortiAnalyzer log monitoring

## Evidence

### IPsec VPN

![IPsec Tunnel](../docs/screenshots/ipsec-tunnel.png)

### SSL-VPN Configuration

![SSL-VPN Configuration](../docs/screenshots/ssl-vpn-config.png)

### SSL-VPN Address Pool

![SSL-VPN Address Pool](../docs/screenshots/ssl-vpn-pool.png)

## Security Note

No VPN credentials, pre-shared keys, private keys, certificates containing sensitive information or other secrets are stored in this repository.
