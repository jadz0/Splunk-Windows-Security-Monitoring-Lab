# Setup Guide

## Lab Components

- Windows VM
- Splunk Enterprise instance
- Splunk Universal Forwarder

## Setup Steps

1. Install Splunk Enterprise on the analysis machine.
2. Enable receiving on the Splunk instance.
3. Install Splunk Universal Forwarder on the Windows VM.
4. Configure the forwarder to collect Windows Event Logs.
5. Forward the logs into Splunk.
6. Confirm ingestion by searching Windows Security events.
7. Generate test events such as successful logons, failed logons, user creation, group changes, and lockouts.
8. Build dashboard panels from SPL queries.

## Suggested Windows Log Inputs

```conf
[WinEventLog://Application]
disabled = 0

[WinEventLog://Security]
disabled = 0

[WinEventLog://System]
disabled = 0
```

## Verification Search

```spl
source="WinEventLog:Security"
```

## Final Deliverable

The final deliverable for this project is a Splunk dashboard that includes summary metrics, authentication visualizations, and investigation tables.