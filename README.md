# sentinel-brute-force-investigation
A hands-on SIEM investigation project using Microsoft Sentinel and KQL to analyze suspicious authentication activity.
# SIEM Security Investigation: Windows Failed Login Detection

## Project Overview

This project demonstrates a practical investigation of failed Windows authentication events using Windows Security Event Logs.

The objective was to analyze Event ID 4625, understand authentication failure details, develop a detection query using Kusto Query Language (KQL), and recommend security improvements.

**Note:** The investigation was performed using local Windows Event Viewer. Microsoft Sentinel was not deployed for this project. The KQL query is prepared for use in a Microsoft Sentinel environment.

## Objectives

- Analyze Windows failed authentication events.
- Understand Windows Security Event IDs 4625 and 4624.
- Interpret authentication failure status codes.
- Develop a KQL query to identify repeated failed logins.
- Document findings and recommend mitigation measures.

## Tools and Technologies

- Windows 11
- Windows Event Viewer
- Windows Security Logs
- Kusto Query Language (KQL)
- GitHub

## Investigation Details

| Field | Finding |
|---|---|
| Event ID | 4625 |
| Event Type | Failed logon |
| Logon Type | 2 – Interactive |
| Status | 0xC000006D |
| SubStatus | 0xC000006A |
| Source Address | 127.0.0.1 – Loopback |

### Key Findings

The event indicated an interactive authentication failure caused by an incorrect password.

The source address was a loopback address, suggesting locally originated activity. A single event is not sufficient evidence of a brute-force attack.

Further correlation with additional authentication events would be required.

## Detection Logic

A KQL query was developed to identify five or more failed authentication attempts associated with the same username and IP address within a 15-minute interval.

See: [Failed Login Detection Query](queries/failed-login-detection.kql)

## Security Recommendations

- Enforce strong password policies.
- Enable multi-factor authentication.
- Monitor repeated failed authentication attempts.
- Correlate failed and successful login events.
- Investigate unusual authentication patterns.

See: [Mitigation Recommendations](recommendations/mitigation.md)

## Project Structure

```text
sentinel-brute-force-investigation/
├── README.md
├── investigation/
│   └── incident-report.md
├── queries/
│   └── failed-login-detection.kql
├── sample-data/
│   └── README.md
├── screenshots/
│   └── event-4625-failed-login.png
└── recommendations/
    └── mitigation.md
```

## Skills Demonstrated

- Windows Security Event Log analysis
- Authentication failure investigation
- Basic incident analysis
- KQL query development
- Security documentation
- Incident response recommendations

## Limitations and Future Improvements

- Collect and analyze multiple authentication events.
- Test the KQL query in a Microsoft Sentinel workspace.
- Correlate failed logins with successful authentication events.
- Develop an alerting rule for suspicious authentication patterns.

## Author

Cybersecurity graduate interested in SOC Analyst and Information Security roles.
