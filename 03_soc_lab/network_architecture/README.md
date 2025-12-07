# Network Architecture Overview

This section documents the network architecture used for the Blue Team Intelligence Capstone. The environment was designed to resemble a small business SOC lab, providing realistic infrastructure for OSINT-driven detection design. While the full environment was successfully ddeployed, instability later hindered live detection testing. As a result, this architecture is presented for reference and to provide context, not as a fully validated detection pipeline. 

See network_diagram.png for a visual of the network.

## High-Level Topology

The Cisco ASA acts as the perimeter firewall, NAT device and DHCP gateway. The Aruba switch provides layer 2 connectivity for all internal systems. Windows hosts and virtual machines simulate user endpoints and SOC infrastructure. This topology supports realistic assumptions for endpoint logs, network flow and firewall logging.

## Addressing Scheme

The internal network uses a flat /24 address space:

| IP Address   | Device              |
| ------------ | ------------------- |
| 192.168.1.1  | Cisco ASA 5506-X    |
| 192.168.1.2  | Aruba Switch        |
| 192.168.1.5  | Security Onion      |
| 192.168.1.7  | Host 1 (Windows 10) |
| 192.168.1.8  | Host 2 (Windows 10) |
| 192.168.1.9  | VM2 (Windows 10)    |
| 192.168.1.10 | VM3 (Windows 10)    |
| 192.168.1.11 | VM4 (Windows 10)    |

Full addressing details are doumented in lan_ip_v1.0.pdf.

## SOC Components

### Security Onion

Security Onion was deployed as a dedicated virtual machine. Its purpose was to ingest logs from the firewall and the elastic agents on the hosts and vms. It's role was to act as the SIEM and analysis platform for detection design. 

### Windows Hosts and VMS

There were two physical Windows hosts, one hosting Security Onion and one hosting three Windows 10 virtual machines via Hyper-V. The virtual machines simulate user systems potentially exposed to malvetising activity. 

## Physical Deployment

The physical lab consists of repurposed enterprise hardware, reflecting realistic constraints of a small SOC environment. 

* Cisco ASA firewall
* Aruba switch
* Desktop hosts runing Hyper-V
* Minimal rack infrastructure

See physical_setup.jpg.

This setup showcased limitations around hardware, power reliability, configuration drift, and recovering after outages. 

## Architectural Limitations

Although the architecture was fully built, several issues limited detection validation. Power loss led to persistent network instability. Firewall and endpoint log ingestion became inconsistent. Reapeated rebuilds consumed time needed for detection assumptions and design decisions. 

## Relevance to the Final
The architecture supports the capstone by providing a realistic environment modela and demonstrating practical SOC design.