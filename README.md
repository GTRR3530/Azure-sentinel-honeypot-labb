# Azure Sentinel Honeypot Lab

## Project Description

This project is a cloud security monitoring lab built using Microsoft Azure and Microsoft Sentinel.

In this lab, I created a Windows virtual machine as a honeypot and collected failed Windows RDP login attempts. The logs were sent to Log Analytics Workspace and analyzed using KQL queries in Microsoft Sentinel.

I also created a Microsoft Sentinel Workbook to visualize failed login attempts on a world map using GeoIP data.

## Tools Used

- Microsoft Azure
- Microsoft Sentinel
- Log Analytics Workspace
- Windows Virtual Machine
- KQL
- Azure Workbook
- GeoIP Dataset

## Project Workflow

1. Created an Azure Resource Group.
2. Deployed a Windows Virtual Machine.
3. Connected the VM to Log Analytics Workspace.
4. Enabled Microsoft Sentinel.
5. Collected Windows Security Events.
6. Queried failed login attempts using KQL.
7. Used GeoIP data to identify country location.
8. Created a Sentinel Workbook map visualization.

## KQL Query Used

```kql
SecurityEvent
| where EventID == 4625
| where isnotempty(IpAddress)
| where IpAddress != "-"
| project TimeGenerated, Computer, TargetAccount, IpAddress

Skills Learned
Azure VM deployment
Microsoft Sentinel setup
Log Analytics Workspace usage
Windows Security Event analysis
KQL basics
Failed RDP login monitoring
SOC-style investigation
Security dashboard creation

Future Improvements
Create Sentinel alert rules
Generate incidents automatically
Add MITRE ATT&CK mapping
Add Logic Apps automation
Monitor multiple virtual machines
Disclaimer

```text
