# Muhammad Huraira — SOC Analyst (Hybrid Detection Engineering & Investigation)

I build hands-on Security Operations Center (SOC) capability through a structured, documentation-first home lab designed to simulate real-world SOC workflows.

My focus is not just deploying tools — but operating like a SOC analyst and detection engineer:

- Designing behaviour-based detections
- Validating endpoint and network telemetry
- Building SOC-grade escalation logic
- Performing structured investigations
- Producing portfolio-level security documentation

This repository documents the progression from endpoint detection engineering to full hybrid (endpoint + network) SOC escalation modelling.

---

# Primary Project

## SOC Home Lab — Hybrid Detection Engineering (Wazuh SIEM)

A production-style SOC environment replicating real monitoring, investigation, prioritization, and escalation workflows.

---

# Architecture

- Wazuh SIEM (Manager / Indexer / Dashboard) on Ubuntu Server
- Windows 11 endpoint onboarded with Wazuh agent
- Sysmon deployed for enriched endpoint telemetry
- Suricata IDS integrated for DNS and TLS network visibility
- Hybrid endpoint + network correlation
- CLI-based operational validation and backend log inspection

---

# Detection Engineering Capability

## Endpoint Detection Engineering

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

## Hybrid Detection Engineering (Endpoint + Network)

Implemented structured correlation between endpoint behaviour and network telemetry:

- Suricata TLS and DNS telemetry ingestion into Wazuh
- Hybrid DNS correlation rules
- Hybrid TLS correlation rules
- External vs internal traffic classification
- Behaviour + network signal alignment
- Noise reduction through allowlisting and downgrade logic

---

# SOC-Grade Prioritization Model (Implemented)

A structured three-tier escalation workflow was engineered:

### Low Confidence (Noise Reduction)
- Microsoft/CDN/telemetry traffic automatically downgraded
- Prevents alert fatigue

### Medium Confidence (Investigation Eligible)
- External TLS to non-allowlisted domains
- Marked as reviewable, not auto-escalated

### High Confidence (SOC Escalation)
- Endpoint behaviour anchor + external TLS to non-allowlisted SNI within defined timeframe
- Production-style escalation logic

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
- Hybrid endpoint + network correlation
- Alert prioritization and escalation modelling
- Backend JSON log validation and analysis
- Detection engineering aligned with MITRE ATT&CK

## Endpoint Monitoring

- Windows Security Event Logs
- Sysmon telemetry analysis
- Process execution behaviour analysis
- File Integrity Monitoring (FIM)

## Network Monitoring

- Suricata IDS integration
- TLS SNI analysis
- DNS telemetry analysis
- Hybrid detection engineering

## Linux & Infrastructure

- Ubuntu Server (CLI-focused administration)
- SSH-based secure management
- Service monitoring and log inspection

## Operational Methodology

- Documentation-first security workflow
- Evidence-driven investigation approach
- Structured detection tuning process
- Analyst-focused reporting and portfolio building

---

# Completed Milestone

Hybrid Detection Engineering (Endpoint + Network)  
Including:

- Behaviour-driven detection
- Hybrid correlation
- Noise suppression logic
- Escalation modelling
- SOC-grade alert prioritization

---

# Future Work (Phase 3 Expansion)

The next phase of this lab will expand visibility into network perimeter telemetry:

- Firewall log ingestion and analysis
- Firewall + endpoint correlation
- East-West traffic monitoring
- Policy-based anomaly detection
- Network-layer threat hunting
- Multi-source correlation (Endpoint + IDS + Firewall)

This phase will focus on strengthening network SOC monitoring capabilities and improving layered detection coverage.

---

# Contact

LinkedIn:
https://www.linkedin.com/in/muhammad-huraira-634a05199
