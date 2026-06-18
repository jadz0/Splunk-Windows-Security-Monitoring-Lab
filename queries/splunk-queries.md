# Splunk Queries

This file contains the SPL queries used in the **Splunk Windows Security Monitoring Lab** dashboard.

## Executive Summary Panels

### Total Failed Logins
```spl
source="WinEventLog:Security" EventCode=4625
| stats count
```

### Total Successful Logins
```spl
source="WinEventLog:Security" EventCode=4624
| stats count
```

### New Accounts Created
```spl
source="WinEventLog:Security" EventCode=4720
| stats count
```

### Account Lockouts
```spl
source="WinEventLog:Security" EventCode=4740
| stats count
```

## Authentication Panels

### Failed Logon Attempts
**Recommended visualization:** Bar chart

```spl
source="WinEventLog:Security" EventCode=4625
| chart count by Account_Name
```

### Successful Logons
**Recommended visualization:** Bar chart

```spl
source="WinEventLog:Security" EventCode=4624
| chart count by Account_Name
```

### Authentication Success vs Failure
**Recommended visualization:** Bar chart

```spl
source="WinEventLog:Security" (EventCode=4624 OR EventCode=4625)
| chart count by EventCode
```

## Investigation Tables

### New User Accounts Created
**Recommended visualization:** Table

```spl
source="WinEventLog:Security" EventCode=4720
| table _time host TargetUserName SubjectUserName
| sort - _time
```

### Users Added to Local Security Groups
**Recommended visualization:** Table

```spl
source="WinEventLog:Security" EventCode=4732
| table _time host TargetUserName Group_Name SubjectUserName
| sort - _time
```

### Account Lockouts
**Recommended visualization:** Table

```spl
source="WinEventLog:Security" EventCode=4740
| table _time host Account_Name Caller_Computer_Name
| sort - _time
```

## Notes

- Field names may vary slightly depending on your Splunk add-ons and parsing.
- If a field does not appear, search the raw event first and adjust the query to the extracted field name in your environment.
- Summary panels are best displayed as **Single Value** visualizations.