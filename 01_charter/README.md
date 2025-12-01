# Project Charter: Blue Team Intelligence

## Project Goal

To design, implement, and document a functional **Blue Team Intelligence** focused on the collection and analysis of Open-Source Intelligence (OSINT) to generate a detection rule.

## Scope

### In Scope
* **Target Environment:** Simulated internal network (VM-based lab).
* **Intelligence Focus:** Malvertising campaigns.
* **Deliverables:** Charter, Weekly Summaries, SOC Lab Build-out, OSINT Report, one Detection Rule, and Final Capstone Report.
* **Tools:** Security Onion, Cisco ASA, Aruba Switch, Desktops, Virtual Machines.

### Out of Scope
* Physical network security assessments.
* Penetration testing or ethical hacking (outside of validating detection rules).
* Policy creation unrelated to the intelligence and detection pipeline.

## Success Criteria

The project will be deemed successful if the team achieves the following:
1.  Successfully **ingest and normalize** logs from log sources.
2.  Produce a comprehensive **OSINT Report** identifying at least 3 unique TTPs and 5 unique IOCs.
3.  Implement and **validate** one custom detection rule in Security Onion.

## Team Roles & Responsibilities

| Role | Team Member | Primary Responsibility |
| :--- | :--- | :--- |
| **Project Lead** | Kyle Hathaway | Final report, overall integration, presentation. |
| **Lab Architect** | Kyle Hathaway | SOC Lab infrastructure build, log pipeline, Security Onion configuration. |
| **Intelligence Analyst** | Kyle Hathaway | OSINT collection, analysis, and report generation (`04_osint_case`). |
| **Detection Engineer** | Kyle Hathaway | Rule creation, validation, and documentation (`05_detections`). |