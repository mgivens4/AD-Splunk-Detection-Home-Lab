# AD-splunk-detection-lab

Active Directory Home Lab with Splunk SIEM

I built a home lab with an Active Directory domain monitored by Splunk. I used it to attack a Windows domain from Kali Linux and then find those attacks in the logs.

Full write-up: AD_Home_Lab_Project_Report_v2.docx

What I Did

Set up a Splunk server and forwarded Windows and Sysmon logs from both Windows machines using the Splunk Universal Forwarder.
Built the lab1.local domain with IT and HR organizational units and test users, and joined a Windows 11 workstation to it.
Brute-forced RDP from Kali with NetExec. Splunk recorded 20 failed logons (Event ID 4625) and then 1 successful logon (Event ID 4624).
Ran an Atomic Red Team test (T1136.001, Create Local Account) and confirmed that it appeared in Splunk.

Tools

Splunk Enterprise · Splunk Universal Forwarder · Sysmon · Active Directory · Kali Linux · NetExec · Atomic Red Team

Key Takeaways

A domain-joined machine has to use the domain controller for DNS.
A wrong clock on the domain controller made the logs look like they were missing.
This was my first time using a SIEM and Atomic Red Team. It was good practice in reading logs and seeing how attacks map to MITRE ATT&CK.