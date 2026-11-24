# Sample Data

## Data Source
Windows Security Event Viewer.

## Event Investigated
- Event ID: 4625
- Event Type: Failed logon
- Logon Type: 2 (Interactive)
- Failure Reason: Unknown user name or bad password
- Status: 0xC000006D
- SubStatus: 0xC000006A
- Source Address: 127.0.0.1 (Loopback)

## Analysis
The event represents a failed interactive authentication attempt caused by an incorrect password.

The source address is a loopback address. This does not indicate an external attacker.

## Privacy Notice
Hostnames, personal usernames, and other identifying information have been excluded from this sample.

This project uses a real Windows event for educational analysis. No actual Microsoft Sentinel deployment or query execution is claimed.
