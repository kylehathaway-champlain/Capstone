# SOC Lab Overview

## Purpose

This directory documents the SOC lab environment used for the Blue Team Intelligence Capstone. The lab was designed to resemble a small business security environment, with realistic infrastructure for log ingestion, visibility, and intelligence informed detecction desgin. Whe the environment was successfully built and partially validated, later instability limited the full detection testing. This lab is presented as architecture and data ingestion proof, not a fully operational detection pipeline.

## Lab Components

The SOC lab consists of the following major components:

### Network Perimeter
#### Cisco ASA 5506-X
Acts as a firewall, NAT device, and DHCP gateway. It provides firewall logs.

### Network Switching
#### Aruba 2530-48G Switch
This provides labyer 2 connectivity. It was configured with SPAN for traffic mirroring. 

### Analysis Platform
#### Security Onion
This is the central log ingestion and analysis platform. It was used to analyze logs and display data in searchable graphs and charts.

### Endpoints
### Windows 10 Hosts and Virtual Machines
There are two physical host machines and three virtual machines. The virtual machines were run on Hyper-V.

## Validation Summary

| Component                   | Status        |
| --------------------------- | ------------- |
| Firewall deployment         | Configured  |
| Switch deployment           | Configured  |
| SPAN configuration          | Implemented |
| Endpoint log ingestion      | Verified    |
| Security Onion dashboards   | Verified    |
| Long-term detection testing |️ Limited    |

Endpoint data ingetion with Elastic Agent was successful. Network and long term detection testing became unstable after power loss and environment rebuilds. 

## Scope and Limitations

There were a few contraints that led to the final outcome of the lab. Power outages led to network instability. Rebuilding introduced configuration drift and time constraints limited how much troubleshooting could be done. Testing the detecctions could not be conducted reliably. 

Rather than presenting incomplete and unverifiable results, the lab is documneted as built, logs ingested but unusable for teseting of detections. 

## Relavance to Final

Although the lab wasn't usable for the final testing, the SOC lab still plays a role in the project by informing what logs would exist in a real environment, demonstrating analyst workflows, grounding detection assumptions in data sources, and supporting OSINT driven design.
Final detection logic is based on log expectations and not verifiable testing results. 

## Final Notes
This SOC lab reflects the kinds of challenges faced in a small SOC evironment. Limited hardware, fragile infrastructure, and competing priorites kept the lab form reaching it's full potential. 