# Secure Server - Hack The Box (HTB) Challenge

## Authors
- Vishal Suman  
- Youssef Elmorsi  
- Jean-Charles Hekamanu  

## Category
- Web Exploitation

## Objective
The aim of this challenge was to compromise a secure server hosted on Hack The Box (HTB) by identifying and exploiting vulnerabilities. The workflow included:
- Reconnaissance  
- Vulnerability Identification  
- Exploitation  
- Privilege Escalation  

## Tools & Techniques Used
- Nmap for service enumeration  
- CVE exploitation (CVE-2024-6387 - OpenSSH signal race condition)  
- Log poisoning  
- Local File Inclusion (LFI) exploitation  
- PHP source code analysis and patching  
- Samba service abuse for webshell deployment  

## Step-by-Step Breakdown

### Service Enumeration
- **Target IP:** `94.237.54.163` (dynamic)
- **Open Ports:**
  - `22/tcp` – OpenSSH 9.2p1 (Debian)
  - `111/tcp` – RPCbind
- **Filtered Ports:** `139, 445` (SMB)
- **UDP Port:** `111/udp` – RPCbind
- **SSH Brute Force:** Disabled (password authentication off)

### Vulnerability Identified
- **CVE-2024-6387:** Race condition in OpenSSH (sshd) leading to unsafe signal handling.

### Exploitation

#### LFI via `projects.php`
- Discovered unvalidated `include()` call:  

Current Status
LFI vulnerability patched.

Webshell verified.

HTB checker still unavailable (port 1337 closed).

Flag capture pending until checker service is accessible.

Conclusion
This project highlights:

Real-world risks of improper file inclusion.

Techniques for exploiting and patching LFI.

Secure coding practices in PHP.

The importance of service hardening and validation mechanisms.

Next Steps:

Retry HTB checker once the service becomes available.

Contact HTB support if issue persists.
