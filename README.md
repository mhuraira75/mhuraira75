# Muhammad Huraira — SOC Analyst (Hybrid Detection Engineering, Perimeter Monitoring, Cloud Identity Detection, Microsoft SOC Engineering, Vulnerability Management & Splunk SOC Operations)

I build hands-on Security Operations Center (SOC) capability through a structured, documentation-first home lab designed to simulate real-world SOC workflows.

My focus is not just deploying tools — but operating like a SOC analyst and detection engineer:

- Designing behaviour-based detections  
- Validating endpoint, IDS, firewall, and cloud telemetry  
- Building SOC-grade escalation logic  
- Performing structured investigations  
- Engineering hybrid multi-layer correlation  
- Translating detection engineering into Microsoft SOC environments  
- Simulating real SOC analyst operational workflows  
- Performing vulnerability assessments and security posture analysis  
- Conducting SIEM investigations using Splunk  
- Producing portfolio-level security documentation  

This repository documents the progression from endpoint detection engineering to full **hybrid (endpoint + network + firewall) SOC escalation modelling**, expanded into **cloud identity detection engineering**, **Microsoft Sentinel / Defender detection engineering**, **SOC operational investigation workflows**, **vulnerability management practices**, and **Splunk SOC detection and investigation workflows**.

---

# Primary Project

## SOC Home Lab — Hybrid Detection Engineering (Wazuh SIEM)

A production-style SOC environment replicating real monitoring, investigation, prioritization, and escalation workflows across multiple telemetry layers.

---

# Architecture

- **Wazuh SIEM** (Manager / Indexer / Dashboard) on Ubuntu Server  
- **Windows 11 endpoint** onboarded with Wazuh agent  
- **Sysmon** deployed for enriched endpoint telemetry  
- **Suricata IDS** integrated for DNS and TLS network visibility  
- **UFW Firewall telemetry** integrated for perimeter monitoring  
- **Cloud identity telemetry ingestion (GitHub activity monitoring)**  
- **Microsoft Sentinel workspace for Microsoft-native detection engineering**  
- **Nessus vulnerability scanner integrated for security posture assessment**  
- **Splunk Enterprise SIEM deployed for investigation and monitoring workflows**  
- Hybrid endpoint + network + firewall + cloud correlation  
- CLI-based operational validation and backend JSON log inspection  

---

# Detection Engineering Capability

## Endpoint Detection Engineering (Phase 1)

- Behaviour-based PowerShell detections  
- Encoded command detection  
- Persistence and privilege escalation monitoring  
- Credential access detection  
- Discovery and defense evasion behaviour analysis  
- Lateral movement visibility  
- LOLBins detection (certutil, mshta, regsvr32)  
- Parent-child process analysis  
- Behaviour chaining and multi-stage attack modelling  

---

## Hybrid Detection Engineering (Endpoint + Network IDS) (Phase 2)

Structured correlation between endpoint behaviour and network telemetry:

- Suricata TLS and DNS ingestion into Wazuh  
- Hybrid DNS correlation rules  
- Hybrid TLS correlation rules  
- External vs internal traffic classification  
- Behaviour + network signal alignment  
- Noise reduction through allowlisting and downgrade logic  

---

## Firewall Detection Engineering (Perimeter Monitoring) (Phase 3)

Phase 3 expanded the lab into perimeter-aware SOC monitoring.

Implemented:

- Firewall telemetry ingestion from UFW  
- Behaviour-based detection for repeated blocked attempts (scan-like activity)  
- Port-focused detections (SIEM-related service ports)  
- Suspicious high-port blocked attempt detection  
- Burst detection using frequency/timeframe modelling  
- Hybrid correlation between IDS telemetry and firewall behaviour  

This phase transitioned the lab from endpoint/network visibility to **true layered defense modelling**.

The environment now supports:

Endpoint telemetry  
+ Network IDS signals  
+ Perimeter firewall behaviour  
= Higher-confidence SOC alerts

---

## Cloud Detection Engineering (Identity Monitoring — Phase 4)

The lab now includes early-stage cloud monitoring capability focused on identity-driven telemetry.

Implemented:

- Custom GitHub telemetry collector script  
- Cloud activity ingestion into Wazuh SIEM  
- JSON-based cloud log parsing  
- Detection engineering for cloud identity events  
- Baseline monitoring for GitHub Push events  
- Cloud identity visibility integrated into SOC workflow  

This represents expansion into **cloud-native SOC monitoring**, where identity events act as primary detection signals.

Focus areas:

- Identity-centric monitoring  
- Cloud activity auditing  
- Behavioural baseline establishment  
- Integration of cloud telemetry into existing SOC escalation logic  

---

## Microsoft SOC Detection Engineering (Sentinel + Defender + KQL — Phase 5)

Phase 5 translated the detection engineering capability developed in the home lab into **Microsoft-native SOC environments**, which are widely used in enterprise SOC teams.

Capabilities implemented:

### Sentinel Architecture Deployment

- Log Analytics Workspace deployment  
- Microsoft Sentinel enablement  
- AzureActivity telemetry ingestion  
- Sentinel analytics rule creation  
- Alert generation and validation  

### KQL Detection Engineering

Detection and hunting queries developed using:

- `where`  
- `summarize`  
- `count`  
- `bin`  
- `join`  

Detection logic built for:

- Rare Azure management operations  
- Control-plane anomaly monitoring  
- Behaviour burst detections  
- Suspicious SIEM hunting activity  
- Multi-signal correlation detections  

### Cross-Source Correlation

Correlation implemented between:

- **LAQueryLogs**  
- **AzureActivity**

Using time-window alignment and cross-table joins to model enterprise SOC detections.

### Defender Investigation Workflow

Validated the Microsoft SOC incident lifecycle:

Telemetry ingestion  
→ Hunting query  
→ Detection rule creation  
→ Alert generation  
→ Incident investigation  

---

# SOC Operational Skills Mini-Labs (Phase 6)

Phase 6 expanded the lab from **detection engineering** into **SOC analyst operational workflows**.

## Phishing Email Investigation

- Email header analysis  
- IOC extraction  
- Domain and URL reputation checks  
- Attachment reputation analysis  
- Threat intelligence enrichment  

## SOAR Automation Exposure

Using the Shuffle platform:

- Alert enrichment workflow design  
- SOC automation pipeline modelling  
- Investigation playbook mapping  

## SOC Incident Investigation Simulation

Simulated a full SOC investigation lifecycle:

Alert  
→ Triage  
→ Investigation  
→ Evidence collection  
→ Escalation decision  
→ Incident documentation  

Investigation included credential execution attempts and behaviour timeline reconstruction.

---

# Linux Investigation & Vulnerability Management (Phase 7)

Phase 7 expanded the SOC lab into **Linux security monitoring and vulnerability management workflows**.

## Linux Security Log Investigation

Performed security investigations using Linux authentication logs.

Activities included:

- SSH authentication failure analysis  
- Detection of repeated login attempts  
- Investigation of successful login events following failed attempts  
- Monitoring sudo privilege escalation activity  
- User account creation monitoring  

Security events were analyzed from:

```
/var/log/auth.log
```

These activities simulated how SOC analysts investigate **Linux authentication anomalies and privilege escalation events**.

---

## Vulnerability Management with Nessus

Deployed **Nessus Essentials** to simulate enterprise vulnerability assessment workflows.

Implementation included:

- Nessus scanner deployment on Ubuntu SIEM server  
- Vulnerability plugin initialization  
- Network vulnerability scanning against Windows endpoint  
- Analysis of scan results and vulnerability severity  

The vulnerability scan evaluated system exposure using:

- Common Vulnerabilities and Exposures (CVE)  
- Common Vulnerability Scoring System (CVSS)  

### Key Findings

Two medium-severity vulnerabilities were identified:

- Untrusted SSL certificate configuration  
- Legacy TLS 1.0 protocol support  

This phase introduced **proactive vulnerability assessment capabilities** alongside detection engineering.

---

# Splunk SOC Detection & Investigation (Phase 8)

Phase 8 expanded the lab into **Splunk SIEM detection engineering and SOC investigation workflows**, reflecting real-world enterprise SOC tooling.

## Splunk Deployment & Log Ingestion

Splunk Enterprise was deployed on the SIEM server and configured to ingest Linux authentication logs.

Implementation included:

- Splunk Enterprise deployment on Ubuntu SIEM server  
- Splunk Web interface configuration  
- File monitoring configuration  
- Ingestion of `/var/log/auth.log` authentication telemetry  
- Validation of real-time log ingestion  
- Generation of SSH authentication failures for telemetry testing  

---

## SPL Detection Engineering

Detection engineering logic was developed using **Splunk Processing Language (SPL)**.

Capabilities implemented:

- Regular expression field extraction using `rex`  
- Username and source IP parsing  
- SSH authentication failure analysis  
- Brute-force detection logic using threshold modelling  
- Sudo privilege escalation activity monitoring  
- Privileged command burst detection  
- Investigation query development for authentication abuse patterns  

---

## Splunk SOC Investigation Workflow

SOC investigation techniques were simulated using Splunk search and pivoting capabilities.

Investigation activities included:

- SSH authentication failure investigation  
- Attacker source IP profiling  
- Targeted username analysis  
- Authentication attack timeline reconstruction  
- Investigation of privileged sudo command activity  
- Correlation between authentication failures and privileged actions  

These activities replicate how SOC analysts investigate **authentication abuse and potential compromise scenarios**.

---

## Splunk Security Monitoring Dashboard

A Splunk dashboard was developed to visualize authentication attacks and privileged activity across the environment.

Dashboard panels included:

- Failed SSH login attempts over time  
- Top attacker source IP addresses  
- Most targeted usernames  
- Sudo privilege activity timeline  
- Total authentication failure volume  
- Top users executing privileged commands  

These dashboards simulate real SOC monitoring panels used to maintain situational awareness of authentication and privilege activity within monitored systems.

---

# SOC Investigation Workflow (Portfolio Work)

Performed full end-to-end SOC investigations using real telemetry:

- Alert queue triage  
- Timeline reconstruction  
- Process lineage analysis  
- Behaviour chain investigation  
- Artifact validation  
- MITRE ATT&CK mapping  
- Risk classification  
- Detection tuning recommendations  

---

# Skills & Technical Capabilities

## SIEM & SOC Operations

- Wazuh SIEM deployment and administration  
- Splunk Enterprise investigation workflows  
- SPL detection engineering and search analytics  
- Microsoft Sentinel architecture and analytics rules  
- KQL threat hunting and detection engineering  
- Hybrid multi-source correlation  
- Alert prioritization and escalation modelling  
- Detection engineering aligned with MITRE ATT&CK  

## Endpoint Monitoring

- Windows Security Event Logs  
- Sysmon telemetry analysis  
- Process execution behaviour analysis  
- File Integrity Monitoring (FIM)

## Network & Perimeter Monitoring

- Suricata IDS integration  
- DNS telemetry analysis  
- TLS SNI inspection  
- Firewall log monitoring (UFW)

## Vulnerability Management

- Nessus vulnerability scanning  
- Security posture assessment  
- Vulnerability severity analysis  
- CVE and CVSS interpretation  
- Security remediation recommendation analysis  

## Cloud Monitoring

- Cloud identity telemetry ingestion  
- GitHub activity monitoring  
- JSON log pipeline engineering  
- AzureActivity telemetry monitoring  

## Microsoft Security Stack

- Microsoft Sentinel deployment  
- KQL threat hunting  
- Cross-table correlation detections  
- Microsoft Defender investigation workflow  

## Linux & Infrastructure

- Ubuntu Server administration  
- SSH security monitoring  
- Linux authentication log analysis  
- Privilege escalation monitoring  

---

# Operational Methodology

- Documentation-first security workflow  
- Evidence-driven investigation approach  
- Behaviour-based detection modelling  
- Layered telemetry correlation  
- Structured vulnerability assessment  
- Analyst-focused reporting and portfolio development  

---

# Completed Milestones

- Endpoint Detection Engineering  
- Hybrid Detection Engineering (Endpoint + IDS)  
- Firewall Detection Engineering (Perimeter Monitoring)  
- Hybrid Multi-Layer Correlation (Endpoint + IDS + Firewall)  
- SOC Escalation Modelling  
- Cloud Identity Detection Engineering  
- Microsoft Sentinel Detection Engineering (KQL + Defender Workflow)  
- SOC Operational Skills Mini-Labs  
- Linux Security Investigation  
- Vulnerability Management with Nessus  
- **Splunk SOC Detection Engineering**  
- **Splunk SOC Investigation Workflows**  
- **Splunk Security Monitoring Dashboard Development**

---

# Contact

LinkedIn:  
https://www.linkedin.com/in/muhammad-huraira-634a05199
