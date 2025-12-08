# Security Onion - Log Ingestion and Analysis Platform

This section documents the deployment and use of Security Onion as the central analysis platform for the Blue Team Intelligence Capstone. Security Onion was used to ingest endpoint and system logs. Although live detection testing not possbile due to lab instability, Security Onion successfully ingested and displayed data from multiple sources, demonstrating functional data collection and visibility. 

## Platform Overview

* Platform: Security Onion v 1.0
* Components Used:
	* Elastic Fleet
	* Elastic Agent
	* Suricata
	* Alert
	* Hunt
	* Detections
	* Dashboards
* Role: Central SIEM and log analysis platform

Security Onion provided a single pane of glass for endpoint events, system logs and agent state information. 

See initial_so_dashoard.png to see the interface after initial install.

## Endpoint Log Ingestion via Elastic Agent

Elastic Agents were deployed to Windows hosts and virtual machines and enrolled through Fleet using a centralized agent policy.

### Agent Policy Configuration

The initial and only configuration of the agent used was the default policy endpoints-initial.
* Elastic Defend: Provides endpoint security features like malware, ransomware, and malicious behavior protection, as well as attack surface reduction and device control.
* Osquery Manager: Allows for real-time and scheduled queries of endpoint data.
* System Integration: Collects system metrics and logs.
* Windows Integration: Specifically for Windows endpoints, this integration collects logs like Windows Event Logs.

Agents reporte healthy status and successfully applied policies, confirming communication between endpoint and the Security Onion manager.

See elastic_agent_config.png to see the initial policy package.

## Evidence of Successful Ingestion

Log ingestion was verified using multiple Security Onion views:

### Hunt Interface

* Elastic Agent lifecycle eventts confirmed agent enrollment and policy updates.
* Endpoint data appreared in the Hunt interface.
* Events included system, authentication, registry, process and configuration activity.

See elastic_agent_evidence.png for the Hunt dashboard confirming agent connection and configuration.

### Dashboards

The Security Onion overview dashboard refelcted active ingestion pipelines, healthy agent status, and baseline system activity. This validated the platform's readiness for analysis.
The dashboard shows multiple event categories, dataset diversity across Windows, Elastic Agent and system sources. These views confirmed that data was present and searchable across the environment. 

See full_ingestion_of_logs.png.

## Limitations

Although log ingestion was successfully demonstrated, later stages of the project encountered network instability following power loss, inconsistent long ingestion after environment rebuilds, and reduced time available for detection rule testing.
As a result, Security Onion is documented as a validated ingestion and analysis platfrom. Detection rules are treated as design artifacts and not executed detections. Log data is used to inform detection logic rather than quantitative metrics. 

## Relevance to the Final

Security Onion supports the capstone by:
* Demonstrating real-world endpoint log ingestion
* Providing evidence of analyst visibility into system behavior 
* Reinforcing small SOC architectural considerations.

It reamains a central component of the project, even without full detection execution. 