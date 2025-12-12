# OSINT Investigation Overview

## Purpose

This directory documents the open source intelligence investigation conducted as part of the Blue Team Intelligence Capstone. The OSINT work focused on identifying malicious software downloads impersonating legitimate tools. Unlike later lab components, the OSINT investigation was completed successfully and serves as the base for the project's detection design.

## Research Question

How do malware campaigns use malicious advertising to spread malware through fake download sites?

## Investigation Methodology

The OSINT process followed a repeatable workflow:

1. Finding suspicious domains serving popular software installers
2. Confimaiton using multiple independent OSINT platforms
3. Documentation of findings with screenshots, verdicts and source citations

The investigation used publicly available tools:

* URLhaus
* urlscan.io
* VirusTotal
* Hybrid Analysis
* Triage
* Intezer
* MalwareBazaar

## File Structure

### Investigation Logs

* osint_inestigation_log_v0.01.pdf
Initial investigation log documenting early findins and domain confirmations

* osint_inestigation_log_v0.02.pdf
Expanded and refined investigation log with improved structure, additional behaviroal notes, and clear vedict

### Appendices

* osint_inestigation_appenix_1.pdf
Supporting screenshots and evidence for early confirmed malicious domains

* osint_inestigation_appenix_2.pdf
Consolidated appendix containg detailed evidence for three confirmed malicious domains

## Key Findings Summary

Across both investigation versions a few patterns emerged. Attackers used domains that impersonated legitimate tools. The malware was delivered by direct executable download and often had behavirol indicators that included process injection, registry modification, persistence mechanisms and evasion techniques. These finidngs later infomred detection design, even when live detection became impossible.

## Relationship to Final

The OSINT investigation forms the foundation of the capstone. It provides real world malware examples, supplies concrete indicatiors and behaviors and bases detection logic in obsereved attacker techniques.