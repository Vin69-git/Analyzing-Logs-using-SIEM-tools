# Analyzing Logs Using SIEM Tools (LetsDefend SOC Environment)

## Project Overview
This repository contains the environment setup parameters, operational guidelines, and procedural analysis methodologies for investigating system security incidents. The practical labs utilize the **LetsDefend** simulated Security Operations Center (SOC) framework to analyze host-level logs, firewall telemetry, and malicious network traffic.

## Repository Contents
* **`Setup`**: Technical environment baseline, architectural constraints, and configuration parameters required to ingest system event data.
* **`Procedure.pdf`**: Structured analyst playbooks, step-by-step incident response logs, and vulnerability mitigation reporting.
* **`README.md`**: Project blueprint and engineering competencies index.

## Core Defensive Competencies
* **Log Aggregation:** Centralizing multi-source event telemetry (Syslog, Windows Event Logs/EVTX, Auth.log) into a central monitoring pane.
* **Threat Detection & Identification:** Writing correlation logic patterns to flag indicators of compromise (IoCs), brute-force authentication streams, and abnormal protocol handshakes.
* **Network Trariage:** Filtering packet metadata and firewall logs to determine traffic legitimacy and drop threat vectors early in the kill chain.
