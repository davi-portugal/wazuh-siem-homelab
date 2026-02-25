# Wazuh SIEM Home Lab (Docker + Ubuntu ARM64 VM)

## Objective
Build a small SIEM lab to monitor an endpoint, validate log ingestion, and generate security-relevant events for investigation.

## Architecture
- macOS host: Wazuh single-node stack (manager + indexer + dashboard) via Docker
- Ubuntu ARM64 VM (UTM): Wazuh agent enrolled to the manager

## Tech
Docker Compose, Wazuh 4.9, Ubuntu 24.04 ARM64 (UTM), Linux auth logs

## What I did
- Deployed Wazuh stack using Docker Compose
- Enrolled an Ubuntu VM as an endpoint (agent name: ubuntu-lab)
- Generated test events:
  - Local account creation/deletion
  - Sudo authentication activity
  - Basic nmap scan (local)

## Evidence (Screenshots)
See the screenshots in the screenshots folder.
1. Endpoint enrolled and Active
2. Agent service running on Ubuntu
3. Security events visible in Wazuh
4. Alert/event detail view

## Notes / Next steps
- Add file integrity monitoring (FIM) rules for sensitive paths
- Add custom alert rules and dashboards
- Expand to a second endpoint and compare baselines
