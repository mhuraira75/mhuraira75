# Muhammad Huraira — SOC Analyst (Hybrid Detection Engineering, Perimeter Monitoring & Cloud Identity Detection)

I build hands-on Security Operations Center (SOC) capability through a structured, documentation-first home lab designed to simulate real-world SOC workflows.

My focus is not just deploying tools — but operating like a SOC analyst and detection engineer:

- Designing behaviour-based detections  
- Validating endpoint, IDS, firewall, and cloud telemetry  
- Building SOC-grade escalation logic  
- Performing structured investigations  
- Engineering hybrid multi-layer correlation  
- Producing portfolio-level security documentation  

This repository documents the progression from endpoint detection engineering to full **hybrid (endpoint + network + firewall) SOC escalation modelling**, now expanded into **cloud identity detection engineering**.

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

# SOC-Grade Prioritization Model (Implemented)

A structured three-tier escalation workflow was engineered:

## Low Confidence (Noise Reduction)

- Microsoft/CDN/telemetry traffic automatically downgraded  
- Prevents alert fatigue  

## Medium Confidence (Investigation Eligible)

- External TLS to non-allowlisted domains  
- Marked as reviewable, not auto-escalated  

## High Confidence (SOC Escalation)

- Endpoint behaviour anchor  
- External TLS to non-allowlisted SNI  
- Firewall repeated block behaviour within defined timeframe  

This mirrors real SOC prioritization and escalation processes.

---

# SOC Investigation Workflow (Portfolio Work)

Performed full end-to-end SOC investigations using real telemetry:

- Alert queue triage  
- Timeline reconstruction  
- Process lineage analysis  
- Behaviour chain investigation  
- Artifact validation (hashing, content inspection)  
- MITRE ATT&CK mapping  
- Risk classification (benign vs suspicious vs malicious)  
- Detection improvement and tuning recommendations  

All investigation reports and detection documentation are included in this repository.

---

# Skills & Technical Capabilities

## SIEM & SOC Operations

- Wazuh SIEM deployment and administration  
- Hybrid multi-source correlation (Endpoint + IDS + Firewall + Cloud)  
- Alert prioritization and escalation modelling  
- Backend JSON log validation and analysis  
- Detection engineering aligned with MITRE ATT&CK  

## Endpoint Monitoring

- Windows Security Event Logs  
- Sysmon telemetry analysis  
- Process execution behaviour analysis  
- File Integrity Monitoring (FIM)  

## Network & Perimeter Monitoring

- Suricata IDS integration  
- TLS SNI analysis  
- DNS telemetry analysis  
- Firewall log analysis (UFW)  
- Scan detection and port anomaly monitoring  
- Hybrid perimeter correlation  

## Cloud Monitoring

- Cloud identity telemetry ingestion  
- GitHub activity monitoring as cloud audit source  
- JSON log pipeline engineering  
- Identity-based detection modelling  
- Cloud event baseline development  

## Linux & Infrastructure

- Ubuntu Server (CLI-focused administration)  
- SSH-based secure management  
- Service monitoring and log inspection  

---

# Operational Methodology

- Documentation-first security workflow  
- Evidence-driven investigation approach  
- Structured detection tuning process  
- Behaviour-based detection modelling  
- Layered telemetry correlation  
- Analyst-focused reporting and portfolio building  

---

# Completed Milestones

- Endpoint Detection Engineering  
- Hybrid Detection Engineering (Endpoint + IDS)  
- Firewall Detection Engineering (Perimeter Telemetry Integration)  
- Hybrid Multi-Layer Correlation (Endpoint + IDS + Firewall)  
- SOC-Grade Escalation Modelling  
- Initial Cloud Identity Detection Engineering Integration  

---

# Future Direction

Continue expanding cloud detection engineering including:

- Authentication anomaly detection  
- Privilege escalation monitoring  
- Password spray modelling  
- Impossible travel detection logic  
- Token/session anomaly detection  
- Full hybrid correlation:

Endpoint  
Network  
Perimeter  
Cloud Identity  

---

# Contact

LinkedIn:  
https://www.linkedin.com/in/muhammad-huraira-634a05199
