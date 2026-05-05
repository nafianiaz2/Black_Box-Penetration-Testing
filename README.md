# Black_Box-Penetration-Testing
Black-box penetration test against Jangow01 vulnerable VM — achieving full root compromise through command injection, credential exploitation, and kernel privilege escalation.
# Jangow01 - Penetration Testing Report
### CSI_7_PTE - Penetration Testing and Ethical Hacking | LSBU 2025/26

## Overview
A full black-box penetration test conducted against the Jangow01 
vulnerable virtual machine from VulnHub. The assessment resulted 
in complete system compromise achieving root-level access through 
a chain of five exploitable vulnerabilities.

## Target
- Machine: Jangow01 v1.0.1 (VulnHub)
- OS: Ubuntu Linux 16.04
- IP: 192.168.56.118
- Attacker: Kali Linux (nafia28) - 192.168.56.101

## Attack Chain
1. OS Command Injection (busque.php) — CVSS 9.8 Critical
2. Plaintext credentials exposed in config.php
3. Password reuse — FTP access as jangow01
4. PHP web shell uploaded via world-writable directory
5. Reverse shell on port 443 (bypassed egress firewall)
6. Kernel exploit CVE-2017-16995 (45010.c) — root obtained

## Tools Used
- Nmap — port and service scanning
- Gobuster — web directory enumeration
- WPScan — WordPress enumeration
- Netcat — reverse shell listener
- Searchsploit — kernel exploit discovery
- GCC — exploit compilation
- FTP client — file transfer to target

## Vulnerabilities Found
| Vulnerability | CVSS | Severity |
|---|---|---|
| OS Command Injection | 9.8 | Critical |
| Plaintext Credentials | 9.8 | Critical |
| Password Reuse | 8.1 | High |
| World-Writable Directory | 7.2 | High |
| Outdated Kernel CVE-2017-16995 | 7.8 | High |

## Result
Full root access achieved. 
Flag: da39a3ee5e6b4b0d3255bfef95601890afd80709

## Disclaimer
This penetration test was conducted in a controlled lab 
environment against a deliberately vulnerable machine with 
full authorisation. All activities were performed for 
educational purposes only as part of academic coursework.
