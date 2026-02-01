# Kerberos Authentication Security Lab

This project documents a network security lab focused on
Kerberos authentication within a Windows Active Directory environment.

The lab simulates real-world authentication traffic, demonstrates a
Kerberoasting attack scenario, and implements monitoring and mitigation
techniques using firewall controls, packet analysis, and intrusion detection.

## Lab Environment
- pfSense firewall (multi-network routing & policy enforcement)
- Windows Server (Domain Controller)
- Windows 11 Client
- Kali Linux
- Wireshark
- Snort IDS
- Rubeus & Hashcat (attack simulation)

## Network Architecture
- Segmented networks (172.16.x.0/24 and 192.168.x.0/24)
- Controlled access between client and domain controller via pfSense
- DNS and routing enforced to support Kerberos authentication flows

## Key Security Activities
### Kerberos Traffic Analysis
- Captured AS-REQ / AS-REP and TGS-REQ / TGS-REP traffic using Wireshark
- Identified encrypted service tickets targeted in Kerberoasting attacks

### Attack Simulation
- Simulated Kerberoasting using Rubeus
- Extracted service ticket hashes for offline analysis
- Validated authentication flow behavior without exposing credentials

### Monitoring & Detection
- Created Snort rules to detect Kerberos TGS-REQ activity on port 88
- Analyzed Windows Event Logs (Event IDs 4768 & 4769) for abnormal patterns

### Mitigation Strategies
- Enforced strong service account password policies
- Recommended AES-only Kerberos encryption
- Reduced attack surface through privilege separation and SPN hygiene

## Notes
No real credentials, public IPs, or sensitive data are included.
