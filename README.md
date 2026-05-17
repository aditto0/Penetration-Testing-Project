# Penetration-Testing-Project
# Web Application Reconnaissance & Applied Penetration Testing Notes

This repository contains command snippets and tool outputs extracted from two academic cybersecurity reports:

- `Web_Application_Reconnaissance.pdf` - Web Application Reconnaissance
- `Penetration_Test_Project.pdf` - Applied Penetration Test Engineering Mid-Term Exam Report

> **Ethical use only:** Run these commands only in authorized labs, owned systems, or environments where you have explicit written permission. Do not use these notes for unauthorized scanning, brute forcing, exploitation, or credential attacks.

## Repository Contents

```text
.
├── README.md
├── extracted_codes.txt
├── Web_Application_Reconnaisance.pdf              # optional source report
└── Penetration_test_Project.pdf      # optional source report
```

## What Is Included

`Commands.txt` contains all extracted command/code-like snippets from the PDFs, grouped by source file and page/section. It includes:

- WHOIS, DNS, MX, and name-server lookup commands
- Email/host enumeration output visible in the report
- WAF and technology fingerprinting commands
- Metasploit module paths and session commands
- John the Ripper and Hydra command examples
- Wireshark display filters and traffic-analysis keywords
- FTP command keywords shown in the exam report

## Command Index

### Reconnaissance

```bash
whois google.com
nslookup -type=mx seu.edu.bd
dig google.com
nslookup -type=ns google.com
```

### WAF and Technology Fingerprinting

```bash
wafw00f -l
wafw00f seu.edu.bd
whatweb seu.edu.bd
whatweb -v -a 3 seu.edu.bd
```

### Metasploit Post-Exploitation

```text
meterpreter > arp
meterpreter > getsystem
msf6 > use post/multi/recon/local_exploit_suggester
msf > use exploit/windows/smb/psexec
msf > use auxiliary/scanner/portscan/tcp
```

Example Metasploit port-scan setup shown in the report:

```text
msf auxiliary(scanner/portscan/tcp) > set RHOSTS 192.168.56.1
msf auxiliary(scanner/portscan/tcp) > set PORTS 4444
msf auxiliary(scanner/portscan/tcp) > run
```

### Password and Hash Testing

```bash
john password1.txt
john hash1.txt --wordlist=password1.txt
hydra ssh://192.168.235.134 -L user.txt -P pass.txt -V -f -t 4
```

### Wireshark and Network Traffic Analysis

```text
http.request.method == "POST"
application/x-www-form-urlencoded
Follow TCP Stream
USER
PASS
LIST
CWD
RETR
STOR
```

## Topics Covered

- Domain registration and DNS reconnaissance
- Mail exchange and name-server discovery
- Web application firewall fingerprinting
- Web technology fingerprinting
- Metasploit post-exploitation modules
- Local privilege escalation checks
- Pass-the-hash-related Metasploit module identification
- TCP port scanning from Metasploit
- Password cracking and SSH brute-force command structure
- Wireshark HTTP POST filtering
- ARP traffic interpretation
- FTP session reconstruction using TCP stream following


## Disclaimer

This project is for academic and defensive cybersecurity learning. The author and repository maintainers are not responsible for misuse of the commands or techniques documented here.
