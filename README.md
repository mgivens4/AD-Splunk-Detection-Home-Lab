AD-Home-Lab-Splunk: Home lab project building a Splunk-monitored Active Directory domain and simulating attacks with Kali Linux, NetExec, and Atomic Red Team
Active Directory Home Lab with Splunk SIEM
Overview

A hands-on cybersecurity home lab focused on how attacks against an Active Directory environment show up in a SIEM. I built a Windows domain, forwarded endpoint and Sysmon logs to Splunk, attacked the domain from Kali Linux, and then traced the activity through the logs.

Full report: AD_Home_Lab_Project_Report_v2.pdf

Tools Used
Windows Server — Active Directory domain controller (lab1.local)
Windows 11 Pro — Domain-joined target workstation
Splunk Enterprise — SIEM for log collection and search
Splunk Universal Forwarder — Sends Windows event logs to Splunk
Sysmon — Detailed endpoint telemetry
Kali Linux — Attack platform
NetExec — RDP brute forcing
Atomic Red Team — MITRE ATT&CK technique simulation
Skills Demonstrated
Active Directory setup and administration (OUs, users, domain join)
SIEM deployment and log forwarding
Windows event log analysis (Event IDs 4624, 4625, 4634)
Attack simulation and MITRE ATT&CK mapping
Troubleshooting (DNS, Windows editions, time sync)


Key Finding
An RDP brute-force attack from Kali showed up in Splunk as 20 failed logons (Event ID 4625), then 1 successful logon (Event ID 4624). The failures were only milliseconds apart, which points to an automated tool rather than a person typing passwords. At first, the attack seemed to leave no logs at all. The cause was the domain controller's clock being wrong, not a broken log pipeline. This shows that accurate time sync is essential for useful logs and investigations.
