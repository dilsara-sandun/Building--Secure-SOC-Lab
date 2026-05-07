# ELK Stack SOC Home Lab: Deployment & Troubleshooting Guide 🛡️
A guide to deploying Elastic Stack with Windows 10 &amp; Sysmon, focusing on resolving real-world connectivity and resource issues.

Overview
This project documents the deployment of an Elastic (ELK) Stack for security monitoring, using a Windows 10 VM as the endpoint. The focus is on real-world troubleshooting of connectivity, security hardening, and resource management.

Lab Environment

SIEM Platform: Elastic Stack (Elasticsearch & Kibana 8.x).

Endpoint: Windows 10 VM integrated via Elastic Agent.

Logging Source: Sysmon (System Monitor).

Network: Local host-to-VM communication.

Key Technical Steps & Challenges
1. Security Hardening
Generated Kibana Encryption Keys to secure session information and ensure Fleet stability.

2. Solving Connectivity Issues
Resolved Fleet Initialization errors caused by host IP changes.

Updated Fleet Server Hosts and re-configured Agent Policies to reflect the new infrastructure environment.

3. SSL/TLS Configuration
Handled certificate mismatch issues in a lab setting by configuring ssl.verification_mode: none in Advanced YAML settings.

4. Resource Optimization
Managed high JVM Garbage Collection (GC) overhead and memory pressure (hitting 96% RAM usage).

Optimized background processes to prevent UI freezing and ensure stable log ingestion.

