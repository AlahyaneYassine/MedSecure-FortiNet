# Project Documentation

This directory contains the technical documentation and visual evidence of the MedSecure-FortiNet project.

## Architecture

The `architecture/` directory contains the global network topology.

```text
docs/architecture/
└── network-topology.png
```

The topology presents the main components of the MediClinic infrastructure, including the FortiGate firewalls, network zones, VPN connectivity and security architecture.

## Security Flows

The `diagrams/` directory contains diagrams illustrating the main communication and security flows.

```text
docs/diagrams/
├── ipsec-communication-flow.png
├── ssl-vpn-medical-staff-flow.png
└── patient-portal-flow.png
```

### IPsec Communication Flow

Illustrates the communication between the clinic and remote laboratory through the site-to-site IPsec VPN.

### SSL-VPN Medical Staff Flow

Illustrates the secure remote-access process for authorized medical staff.

### Patient Portal Flow

Illustrates the communication flow associated with the MediClinic patient portal.

## Configuration Evidence

The `screenshots/` directory contains screenshots collected from the virtualized laboratory environment.

```text
docs/screenshots/
├── fortigate-clinique.png
├── fortigate-labo.png
├── switch-trunk.png
├── network-objects.png
├── server-app-admin.png
├── patient-records.png
├── mysql-service-3306.png
├── ipsec-tunnel.png
├── ssl-vpn-config.png
├── ssl-vpn-pool.png
└── fortianalyzer-logs.png
```

These screenshots provide visual evidence of the implemented network, VPN and monitoring configuration.

## Laboratory Environment

The project was designed and deployed in a virtualized cybersecurity laboratory using:

* PNETLab
* VMware Workstation
* FortiGate
* FortiAnalyzer
* Virtual network devices

## Repository Principle

The documentation focuses on the architecture, implementation and validation of the solution.

Sensitive information such as passwords, VPN secrets, private keys, API tokens, license files and real patient data is intentionally excluded.
