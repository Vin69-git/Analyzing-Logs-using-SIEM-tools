# Security Information and Event Management (SIEM) Log Analysis & Incident Response

## Project Overview
This repository documents a comprehensive, hands-on simulation of an enterprise Security Operations Center (SOC) framework utilizing the **LetsDefend** platform. The pipeline focuses on real-time log management, intrusion detection monitoring, and executing structured incident response playbooks to classify, triage, and mitigate advanced threat vectors.

## Technical Artifacts Index
* **`Procedure.pdf`**: End-to-end visual documentation and forensic walkthrough of the SIEM monitoring console, event metadata analysis, and active playbook execution.
* **`Setup`**: Technical environment baseline, telemetry parameters, and log ingestion configurations used to simulate corporate network infrastructure.

---

## Featured Investigation: SOC138 — Suspicious Malicious Payload Triage
A core focus of this project involved taking ownership of **EventID 72 / 77**, a medium-severity alert triggering a `Detected Suspicious xls File` rule on an internal host endpoint (`172.16.17.56` / Sofia).

### 1. Telemetry & Indicator Gathering
* **Target Payload:** `ORDER SHEET & SPEC.xlsm` (Size: 2.66 Mb)
* **Cryptographic Signature:** Hash verification initialized to map the file (`7bef88ea9bba38295b79bb27a59684f2`) against global threat intelligence data.
* **Network Baseline:** Analyzed host-level firewall parameters where the initial perimeter device action was marked as `Allowed`, necessitating immediate manual containment and endpoint triage.

### 2. Playbook Execution & Triage Methodology
* **False Positive Validation:** Executed the formal SOC Playbook sequence to cross-reference system alerts with network behavioral baselines, ensuring accurate incident classification.
* **Payload Isolation:** Conducted sandbox verification and artifact inspection to determine macro-execution intent and protect local host infrastructure from unauthorized remote access or data exfiltration.

---

## Core Engineering Competencies Demonstrated
* **SIEM Operations & Incident Triage:** Active event monitoring across modern threat vectors including brute-force detection, CVE exploitation monitoring (e.g., Palo Alto Networks PAN-OS, Checkpoint Gateway), and credential phishing streams.
* **Endpoint & Threat Intelligence Mapping:** Cross-referencing active session logs with MD5/SHA256 file hashes to run comprehensive asset-impact assessments.
* **Structured Risk Documentation:** Translating live network indicators into formalized Incident Reports mapping directly to standard security framework controls.
