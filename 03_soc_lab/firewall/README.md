# Cisco ASA Firewall - Refereence Configuration

This section documents the Cisco ASA 5506-X firewall used in the SOC lab environmnet. The firewall was used primarily to provide realistic network architecture and to explore firewall generated logs that would support detection design. While the ASA was successfully configured dand logging enabled, the logs played a limited role in the final detections due to lab instability. 

### Device Overview

* Model: Cisco ASA 5506-X
* OS Version: ASA 9.8(2)
* Hostname: vortex
* Deploymnet Type: Routed/bridged internal network
* Role: Perimeter firewall and DHCP gateway

The ASA connects the internal lab network to the internet, providing NAT, DHCP, and policy enforcement for internal hosts and virutal machines. 

### Network Role in the Lab

The firewall was positioned logically between the external nework and the internal SOC lab environment. The outside interface recives IP address via DHCP while the inside interfaces are bridged into a single internal network (192.168.1.0/24). NAT is configured for all internal sements and DHCP provides internal address assignment. This setup emulates a small business environment which is consistent with the target environment of the project.

## Logging Configuration

Firewall logging was enabled to provide logs for ingestion into Security Onion.

### Logging Characteristics

Syslog was enabled at informational severity, the hostname is included as device identifier. Logs were forwarded to 192.168.1.5 and the protocal was UDP/514. The key configuration commands are docuented in logging_config_cmd.txt.

### Files Included

The following files were gathered as evidence:
* initial_config.txt
Baseline configuration prior to enabling external log forwarding.
* logging_config.txt
Firewall configuration after syslog settings were applied.
*logging_config_cmd.txt
Command sequence used to enable syslog forwarding and verify logging status.

These files demonstrated configuration intent and document changes made during the lab build out. 

### Limitations
Although the Cisco ASA was successfully configured and produced syslog events, firewall logs were not used for final detection logic because of lab instability, inconsistent log ingestion and the decision to prioitize intelligence drive detection over live validation.

### Relevance to Final Project
The ASA configuration supports the project by:
* Demonstrating a realistic network perimeter.
* Reinfocing small SOC design considerations.
It is included to support documentaion and realism.