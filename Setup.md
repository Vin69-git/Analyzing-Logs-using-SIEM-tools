# SOC Lab Infrastructure & Telemetry Configuration

This document specifies the technical architecture, log ingestion mechanisms, and network monitoring parameters configured within the LetsDefend enterprise SOC simulation workspace. The lab mirrors a distributed corporate environment to facilitate continuous log aggregation and incident triage.

---

## 🏗️ Network Architecture & Topology

The virtual environment simulates a multi-segment enterprise network divided into distinct logical security zones:

1. **Demilitarized Zone (DMZ):** Hosts public-facing corporate assets, including Web Applications (built on the ColdBox framework) and External Domain/Mail (MX) Exchangers.
2. **Internal Enterprise LAN:** Consists of employee endpoints (e.g., Host Identity: `Sofia` / IP: `172.16.17.56`) running standard operating system baselines.
3. **Security Operations Center (SOC) Management Pane:** Centrally aggregates telemetry data bypassing the perimeter controls for manual analyst inspection.

---

## 🔌 Log Collection & Ingestion Framework

Logs are ingested into the SIEM interface utilizing automated data pipelines to provide a unified monitoring pane:

* **Host-Level Monitoring:** Tracking Windows Security Logs (`Event ID 4624` for successful authentication, `Event ID 4625` for brute-force tracking) and Linux authentication paths (`/var/log/auth.log`).
* **Perimeter Defense Telemetry:** Real-time log forwarding from Next-Generation Firewalls (NGFW), including Palo Alto Networks PAN-OS threat logs and Checkpoint Security Gateway connection tables.
* **Network Forensic Artifacts:** Ingestion of centralized packet capture (PCAP) data to parse handshake parameters, malicious macro callbacks, and data exfiltration patterns.

---

## 🎯 Active Blacklist & Whitelist Configurations

To optimize alert generation and minimize false-positive strain on the monitoring console, the environment enforces strict rule-matching parameters:
* **Signature Blacklisting:** Immediate alert generation upon detecting known malicious indicators of compromise (IoCs), including suspicious macro-enabled payload hashes (e.g., `SOC138` payload matching).
* **Behavioral Whitelisting:** Standardizing normal internal routing behavior to dynamically highlight abnormal long-tail log occurrences, rare process executions, and sudden external directory modifications.
