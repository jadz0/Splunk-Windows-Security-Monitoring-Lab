# Architecture

## Lab Environment

The lab consists of two virtual machines:

### Splunk Server

* Ubuntu Linux
* Splunk Enterprise
* Receives logs from endpoints
* Hosts dashboards and investigations

### Endpoint

* Windows 10 Virtual Machine
* Splunk Universal Forwarder
* Generates Windows Security Events

## Data Flow

Windows Security Logs

↓

Splunk Universal Forwarder

↓

Splunk Enterprise Receiver (Port 9997)

↓

Indexed Events

↓

Dashboards & Investigations

## Monitored Event IDs

| Event ID | Description               |
| -------- | ------------------------- |
| 4624     | Successful Login          |
| 4625     | Failed Login              |
| 4720     | User Account Created      |
| 4732     | User Added to Local Group |
| 4740     | Account Lockout           |

## Security Monitoring Workflow

1. Windows generates security events.
2. Universal Forwarder collects events.
3. Events are sent to Splunk Enterprise.
4. Splunk indexes and stores logs.
5. Dashboards visualize activity.
6. Analysts investigate suspicious events using SPL queries.
