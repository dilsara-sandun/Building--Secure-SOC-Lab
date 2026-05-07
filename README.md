🛡️ ELK Stack SOC Home Lab: Deployment & Troubleshooting Guide
Welcome to my SOC Home Lab project! This repository documents the end-to-end deployment of an Elastic (ELK) Stack for security monitoring, with a focus on solving the real-world technical hurdles that occur in dynamic lab environments.

🏗️ Lab Environment
SIEM Platform: Elastic Stack (Elasticsearch & Kibana 8.x)

Endpoint: Windows 10 VM

Agent: Elastic Agent managed via Fleet

Logging Source: Sysmon (System Monitor) for granular event tracing

Connectivity: Local host-to-VM communication

🔐 Key Technical Steps & Security Hardening
🔑 Encryption Keys Generation
To ensure a production-grade setup and Fleet stability, I generated and configured Kibana Encryption Keys. This secures session information and saved objects within the stack.

🛠️ Challenges & Troubleshooting
🌐 1. Resolving Connectivity & Fleet Initialization
Issue: Encountered Unable to initialize Fleet and ETIMEDOUT errors due to host IP changes.

Solution: Re-configured the Fleet Server Hosts with the updated IP (139.222.22.199) and verified the connection.

🔒 2. Handling SSL/TLS Mismatches
Issue: Certificate mismatch errors when communicating over HTTPS in a local lab setting.

Solution: Configured ssl.verification_mode: none within the Advanced YAML settings to bypass verification while maintaining encrypted flow.

🎯 3. Policy & Output Redirection
Issue: Default Fleet outputs were locked for UI updates.

Solution: Created a Custom Output and successfully re-assigned the Agent Policy to route telemetry data correctly.

🧠 4. Resource & Memory Management
Issue: System hit a critical 96% Memory usage peak, causing high JVM Garbage Collection (GC) overhead and UI freezing.

Solution: Optimized background processes and monitored JVM metrics to stabilize the Elasticsearch service for consistent log ingestion.

📈 Final Result
After successful troubleshooting, the Elastic Agent status reached "Healthy", and real-time Sysmon logs (Event IDs 1, 3, 22) were successfully ingested into the Kibana Dashboard.
