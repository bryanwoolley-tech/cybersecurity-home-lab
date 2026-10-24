# Lab 03: SSH Authentication & Security Log Analysis

## Overview

This lab demonstrates SSH authentication monitoring and security event investigation in a controlled Linux environment.

Using Kali Linux as the testing workstation and Ubuntu Server as the target system, I generated an unsuccessful SSH authentication attempt and investigated the resulting security logs.

The exercise simulates an entry-level Security Operations Center (SOC) investigation involving authentication failures, event identification, and log analysis.

## Lab Objectives

- Understand how SSH authentication works.
- Generate a controlled failed-login event.
- Locate and analyze SSH authentication logs.
- Identify source IP addresses, attempted usernames, and authentication outcomes.
- Document evidence and security recommendations.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Analyst workstation | Kali Linux |
| Target server | Ubuntu Server |
| Kali lab IP | 192.168.56.10 |
| Ubuntu lab IP | 192.168.56.20 |
| Protocol | SSH |
| Destination port | TCP 22 |
| Network | Isolated VirtualBox lab network |

## Methodology

### 1. Establish Network Connectivity

Verify connectivity from Kali to Ubuntu:

```bash
ping -c 4 192.168.56.20
```

The connectivity test previously confirmed successful communication between the two lab machines.

### 2. Generate an Authentication Failure

From the Kali Linux terminal, initiate an SSH connection using a deliberately invalid username:

```bash
ssh fakeuser@192.168.56.20
```

Enter an incorrect password when prompted, then terminate the attempt.

This produces a controlled authentication failure for investigation.

### 3. Investigate Ubuntu SSH Logs

On Ubuntu Server, inspect the SSH service logs:

```bash
sudo journalctl -u ssh -n 20 --no-pager
```

Filter for authentication failures:

```bash
sudo journalctl -u ssh --no-pager | grep -E "Invalid user|Failed password"
```

### 4. Analyze Authentication Events

Examine the available log messages for:

- Attempted SSH username
- Source IP address
- Authentication success or failure
- Event timestamp
- Network source port

## Investigation Findings

| Indicator | Observation |
|---|---|
| Simulated source | Kali Linux |
| Source IP | 192.168.56.10 |
| Target system | Ubuntu Server |
| Destination IP | 192.168.56.20 |
| Attempted username | fakeuser |
| Authentication result | Failed password |
| Attack classification | Controlled failed-login simulation |

Ubuntu generated an authentication failure entry corresponding to the controlled SSH login attempt.

The actual password entered was not included in the SSH authentication logs. This is expected security behavior.

A single controlled failed login does not establish that a brute-force attack occurred.

## Evidence

### Failed SSH Authentication

![SSH Authentication Failure](screenshots/lab03-failed-ssh-login.png)

The screenshot documents the failed SSH authentication event recorded by Ubuntu.

## Security Recommendations

1. Use unique, strong passwords for Linux accounts.
2. Configure SSH public-key authentication.
3. Disable SSH password authentication after verifying key-based access.
4. Limit SSH access using firewall rules.
5. Monitor authentication logs for repeated failures and unusual source addresses.
6. Keep Linux systems and SSH packages updated.

## Skills Demonstrated

- Linux system administration
- SSH authentication analysis
- Security event investigation
- Linux journal inspection using `journalctl`
- Log filtering with `grep`
- Network source identification
- SOC investigation documentation
- VirtualBox lab management

## Conclusion

This lab demonstrated how to generate, identify, and investigate a failed SSH authentication event in a controlled environment.

The exercise provided hands-on experience with Linux security logs and foundational SOC investigation procedures.

**Future enhancement:** Implement SSH key-based authentication and investigate repeated failed logins in a controlled lab scenario.
