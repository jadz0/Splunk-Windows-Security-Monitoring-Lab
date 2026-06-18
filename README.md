# Splunk Windows Security Monitoring Lab

## Overview

This project demonstrates the deployment and configuration of a Splunk-based Security Operations Center (SOC) monitoring environment for Windows Security Logs.

The lab consists of a Windows virtual machine forwarding security events to a Splunk Enterprise server running on Ubuntu. Custom dashboards and detections were created to monitor authentication activity, account management events, and potential security incidents.

## Objectives

* Deploy Splunk Enterprise on Ubuntu
* Configure Splunk Universal Forwarder on Windows
* Ingest Windows Security Event Logs
* Create security monitoring dashboards
* Investigate authentication-related events
* Map detections to MITRE ATT&CK techniques

## Architecture

Windows VM
→ Splunk Universal Forwarder
→ Splunk Enterprise (Ubuntu)
→ Security Monitoring Dashboard

See `docs/architecture.md` for additional details.

## Technologies Used

* Splunk Enterprise
* Splunk Universal Forwarder
* Ubuntu Linux
* Windows 10
* Windows Event Logs
* SPL (Search Processing Language)

## Dashboard Features

* Failed Login Monitoring (Event ID 4625)
* Successful Login Monitoring (Event ID 4624)
* Authentication Success vs Failure Comparison
* New User Account Creation Detection (Event ID 4720)
* User Added to Security Groups Detection (Event ID 4732)
* Account Lockout Monitoring (Event ID 4740)

## Screenshots

### Dashboard Overview

![Dashboard Overview](screenshots/dashboard-overview.png)

### Failed Login Investigation

![Failed Login Investigation](screenshots/failed-login-investigation.png)

## MITRE ATT&CK Mapping

| Event                        | MITRE Technique              |
| ---------------------------- | ---------------------------- |
| Failed Logins                | T1110 - Brute Force          |
| Successful Logins            | T1078 - Valid Accounts       |
| New User Creation            | T1136 - Create Account       |
| User Added to Security Group | T1098 - Account Manipulation |
| Account Lockouts             | T1110 - Brute Force          |

## Skills Demonstrated

* SIEM Administration
* Log Analysis
* Security Monitoring
* Threat Detection
* Incident Investigation
* Windows Security Event Analysis
* Splunk Dashboard Development
* SPL Query Development

## Lessons Learned

This project provided practical experience with SIEM deployment, Windows event monitoring, dashboard creation, and security event investigation. It reinforced the importance of centralized logging and proactive security monitoring in enterprise environments.
