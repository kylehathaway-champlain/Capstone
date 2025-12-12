# Rule Design

## Purpose

This directory contains the detection rule designs created as the final stage to the Blue Team Intelligence Capstone. These rules translate the OSINT investigation into detection rules that a SOC could deploy in a produciton environment. Due to lad instability late in the semester, these rules were not executed or validated in Security Onion. Instead, they are presneted as examples of what could be created from the OSINT investigation.

## Overview of Detection Strategy

The OSINT investigation identified a malware delivery campaign using a malicious domain, puttssh.run and a malicious IP address , 104.21.16.48. These indicators were repatedlly confirmed across multiple OSINT sources and formed the base of the two detections. 

1. DNS Query Detection - Idenfifies attempts to resolve the malicious domain.
2. Outbound IP Communication Detection - Identifies network connections to the malicious IP.

These two rules work together by addressing pre-infection lookup behavior and post lookup network activity.

## Detection Rule 1

### Malicious PuTTY Impersonation Domain - DNS Query Detection

This rule is desinged to alert on any DNA query attempting to resolve the impersonation doamin puttyssh.run.

### Detection Logic

alert dns any any -> any any (msg:"Malicious PuTTY Impersonation Domain Detected (puttyssh.run)"; flow:to_server; dns.query; content:"puttyssh.run"; nocase; classtype:trojan-activity; sid:9000001; rev:1;)

### Purpose 

Detects early stage activiity where a user or malware attempts to lookup the domain associated wiht the malicious downloader.

### Why This Detection Matters

DNS is often the first observable event in a malicious donwload workflow. Detecting domain resolution allows defenders to identify comporomise attempts before the user recieves malware. This rule supports quick remediation becasue it ties directly to a single malicious domain confirmed with OSINT.

## Detection Rule 2

### High Severity Outbound Traffic to Malicious PuTTY Impersonation IP

This rule alerts on any outbound request from an internal host to the malicious IP address identified during the OSINT verification.

### Detection Logic

alert ip $HOME_NET any -> 104.21.16.48 any (msg:"IOC - High Severity Traffic to PuTTY Impersonation IP (104.21.16.48)"; flow:established; classtype:trojan-activity; sid:9000002; rev:1;)

### Purpose

Detects confirmed communication with malware distribution site, an indicator of active compromise or user download attpempts.

### Why This Detection Matters

The IP remained consistently associated with malicious hosting behavior across VirusTotal, URLhaus, Triage, and other OSINT sources. Outbound flow to this IP strongly indicates malicious download activity. THis rule provides network based confimration independent of DNS visibility. 

### Operational Context

In a produciton environment these rules would be paired with suppression lists, alerts enrighments and SOC playbooks.

## Final Scope

These detection rules represent the final output of the project. The SOC lab environment became unstable late in the semester and the rules were not executed or validated inside Security Onion, because of that no packet captures or generated alerts are included.

## Relevance to Final

These detection designs demonstarte interpretation of OSINT indicators, understanding of Suricata rule structure and the ability to convert intelligence into detection logic.