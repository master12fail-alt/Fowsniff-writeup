# Fowsniff - TryHackMe Writeup

**Author:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)  
**Platform:** TryHackMe  
**Room:** [Fowsniff](https://tryhackme.com/room/fowsniff)  
**Difficulty:** Easy  
**Date:** May 10, 2026

---

## Objective
Gain initial access to the Fowsniff Corporate server by exploiting leaked credentials and escalate privileges to root to capture the flag.

---

## Reconnaissance

### Nmap Scan
![Nmap Scan](images/1-nmap..png)

**Open Ports:**
- 22/tcp — OpenSSH 7.2p2 (Ubuntu)
- 80/tcp — Apache httpd 2.4.18
- 110/tcp — POP3 (Dovecot)
- 143/tcp — IMAP (Dovecot)

### Web Enumeration
![Fowsniff Website](images/8-website-breach.png)

The official website confirmed a major data breach involving employee credentials.

---

## OSINT & Credential Leak

### GitHub Leak
![fowsniff.txt](images/2-fowsniff-txt.png)

### Twitter OSINT
![Twitter Search](images/3-osint-twitter.png)

---

## Password Cracking

![Hash File](images/4-hash-file..png)

![John the Ripper](images/5-john-crack.png)

**Cracked Credentials (redacted per THM rules):**
- `seina` → `scooby*****`
- `baksteen` → `S1ck3nBluff********`

---

## Initial Access

### POP3 Exploitation
![POP3 Access](images/6-pop3-email.png)

Retrieved internal emails containing critical information.

### SSH Access
![SSH Login](images/7-ssh-baksteen.png)

Gained user-level access.

---

## Privilege Escalation

After local enumeration, successfully escalated to **root**:

![Root Shell](images/9-root-flag.png)

**Flag Captured!**

---

## Attack Chain Summary

| Phase                  | Technique                        | Tool              |
|------------------------|----------------------------------|-------------------|
| Reconnaissance         | Port Scanning                    | Nmap              |
| OSINT                  | GitHub Leak + Twitter            | Browser           |
| Cracking               | MD5 Dictionary Attack            | John the Ripper   |
| Initial Access         | POP3 + SSH                       | Telnet / SSH      |
| Privilege Escalation   | Local Misconfiguration Exploit   | Bash              |

---

## Lessons Learned

- Exposed POP3 services with weak authentication are extremely dangerous.
- MD5 is considered broken for password storage.
- Accidental leaks on GitHub can lead to full system compromise.
- Proper credential hygiene and service hardening are essential.

---

**Writeup by:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)
