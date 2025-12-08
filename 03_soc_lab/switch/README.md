# Aruba Switch - Network Connectivity and SPAN Configuration

This section documents the Aruba 2530-48G switch used in the SOC lab environment. The switch provided layer 2 connectivity for all internal systems and was configured to support port mirroring for network traffic observation. Although SPAN was successfully configured, network logs from the switch was ultimately not relied upon for final deteciton design due to lab instability. 

## Device Overview

* Model: Aruba 2530-48G
* Hostname: vortex_switch
* Management IP: 192.168.1.2/24
* Default Gateway: 192.168.1.1 (Cisco ASA)

## Network Role in the Lab

It provides switching for all internal devices, hosts the default VLAN for the lab environment and enabled traffic mirroring to support network visibility. 
This configuration mirrors a small business access switch, appropriate for the projects SOC architrecture. 

## SPAN Configuration

SPAN was configured to replicate traffic from a source port to a dediciated destination port intended for monitoring.

### SPAN Design

* Source Port: Interface 1
* Destination Port: Interface 24
* Purpose: Mirror traffic to a monitoring interface connected to Security Onion

Configuration steps are documented in span_script.txt and the post configuration snapshot.

## Configuration Files Included

The following files are included to document configuration intent and execution:
* initial_config.txt
Baseline switch configuration prior to SPAN setup
* span_config.txt
Switch configuration after port mirroring is enabled
* span_script.txt
Command sequence used to configure and verify SPAN

These files demonstrate how traffic mirroring was intended ot support network data collection.

## Limitations

While SPAN configuration was completed, mirrored traffic was not used in the final detection logic due to network instability, data inconsitencies after environment rebuilds and project scope reduction. As a result, the switch and SPAN configuration are retained as reference architecture, not as validated network data sources.

## Relevance to Final

The Aruba switch contributes to the capstone by demonstrating realistic network design, providing architectural context, documenting network visibility techniques and reinforcing limitations found in small SOC environments.