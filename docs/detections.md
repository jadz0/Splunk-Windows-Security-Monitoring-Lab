# Detection Catalog

## Failed Login Detection

### Event ID

4625

### Purpose

Detect failed authentication attempts that may indicate brute-force activity.

### MITRE ATT&CK

T1110 - Brute Force

### Investigation Steps

* Identify targeted accounts
* Review source hosts
* Count repeated failures
* Determine whether lockouts occurred

---

## Successful Login Detection

### Event ID

4624

### Purpose

Monitor successful authentication activity.

### MITRE ATT&CK

T1078 - Valid Accounts

### Investigation Steps

* Verify account legitimacy
* Review login frequency
* Identify unusual login patterns

---

## New User Account Creation

### Event ID

4720

### Purpose

Detect creation of new user accounts.

### MITRE ATT&CK

T1136 - Create Account

### Investigation Steps

* Identify account creator
* Validate authorization
* Review account purpose

---

## User Added to Local Security Group

### Event ID

4732

### Purpose

Detect privilege escalation and group membership changes.

### MITRE ATT&CK

T1098 - Account Manipulation

### Investigation Steps

* Identify modified account
* Review group assignment
* Verify administrative approval

---

## Account Lockout Detection

### Event ID

4740

### Purpose

Detect accounts that have been locked due to repeated authentication failures.

### MITRE ATT&CK

T1110 - Brute Force

### Investigation Steps

* Determine source of failures
* Review targeted account
* Investigate potential brute-force attempts
