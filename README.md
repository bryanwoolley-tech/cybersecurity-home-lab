# Cybersecurity Home Lab

Hands-on cybersecurity lab environment built to develop practical skills in networking, Linux administration, network reconnaissance, packet analysis, security monitoring, and incident investigation.

## Lab Environment

- Kali Linux
- Ubuntu Server
- Oracle VirtualBox
- Wireshark
- Nmap
- OpenSSH
- Isolated virtual lab network

## Lab Progress

- [x] VirtualBox installation and configuration
- [x] Kali Linux deployment
- [x] Ubuntu Server deployment
- [x] OpenSSH Server installation
- [x] Isolated Kali-to-Ubuntu network configuration
- [x] Kali-to-Ubuntu connectivity
- [x] SSH remote access from Kali to Ubuntu
- [x] Nmap service discovery
- [X] Linux authentication log analysis
- [ ] Firewall configuration and testing
- [ ] Wireshark packet analysis
- [ ] SOC-style incident investigation
- [ ] SIEM / Splunk integration
- [ ] Additional vulnerable target systems
- [ ] Active Directory security lab

---

# Completed Labs

## Lab 01 — Network Connectivity & SSH

Built an isolated virtual network between Kali Linux and Ubuntu Server.

### Skills Demonstrated

- Virtual machine networking
- Linux network configuration
- IP addressing
- ICMP connectivity testing
- OpenSSH configuration
- SSH remote administration

[View Lab 01](01-network-connectivity/)

---

## Lab 02 — Nmap Service Discovery

Performed authorized network reconnaissance from Kali Linux against an Ubuntu Server target.

### Activities

- Verified target availability
- Performed TCP port discovery
- Identified exposed services
- Conducted service/version detection
- Identified SSH on TCP port 22
- Captured Nmap-generated network traffic with Wireshark
- Analyzed TCP and SSH traffic
- Preserved the packet capture as PCAPNG evidence

### Tools

`Nmap` `Wireshark` `Kali Linux` `Ubuntu Server` `OpenSSH`

### Evidence

The Lab 02 repository contains:

- Technical lab documentation
- Nmap scan evidence
- Wireshark packet analysis screenshot
- Original `.pcapng` packet capture

[View Lab 02](02-nmap-service-discovery/)

---

# Upcoming Labs

## Lab 03 — Linux Authentication Log Analysis

Generate controlled SSH authentication activity and analyze Ubuntu authentication logs to distinguish successful and unsuccessful login attempts.

## Lab 04 — Firewall Configuration & Testing

Configure Ubuntu firewall rules and test how access-control changes affect network connectivity and exposed services.

## Lab 05 — Wireshark Packet Analysis

Capture and analyze:

- ARP
- ICMP
- TCP
- SSH
- Source and destination IP addresses
- Source and destination ports
- TCP three-way handshake

## Lab 06 — SOC-Style Investigation

Analyze simulated suspicious activity using network traffic, Linux logs, and other available evidence to develop an incident timeline and findings.

## Future Expansion

- SIEM / Splunk integration
- Vulnerable target systems
- Security monitoring
- Incident detection
- Active Directory security lab

## Documentation Standard

Each lab will document:

1. Objective
2. Environment
3. Network configuration
4. Tools used
5. Commands used
6. Screenshots
7. Results
8. Findings
9. Remediation or defensive considerations
10. Lessons learned

## Legal and Ethical Scope

All security testing documented in this repository is conducted against systems owned and controlled within this private virtual lab environment.

Testing is performed for educational, defensive security, and authorized cybersecurity training purposes only.
