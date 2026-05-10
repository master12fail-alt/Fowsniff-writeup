# Fowsniff - TryHackMe Writeup

**Author:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)  
**Platform:** TryHackMe  
**Room:** [Fowsniff](https://tryhackme.com/room/fowsniff)  
**Difficulty:** Easy  
**Date:** May 10, 2026

---

## Objective
Exploit a data breach at Fowsniff Corporation to gain initial access and escalate privileges to root.

---

## Reconnaissance

### Nmap Scan
![Nmap Scan](images/1-nmap..png)

**Open Ports:**
- 22 (SSH)
- 80 (HTTP)
- 110 (POP3)
- 143 (IMAP)

### Web Enumeration
![Fowsniff Website](images/8-website-breach.png)

---

## OSINT - Credential Leak

### GitHub Leak
![fowsniff.txt](images/2-fowsniff-txt.png)

### Twitter OSINT
![Twitter Search](images/3-osint-twitter.png)

---

## Password Cracking

![Hash File](images/4-hash-file..png)

![John Cracking](images/5-john-crack.png)

**Cracked Credentials (redacted):**
- `seina` → `scooby*****`
- `baksteen` → `S1ck3nBluff********`

---

## Initial Access via POP3

![POP3 Access](images/6-pop3-email.png)

---

## SSH Access

![SSH Login](images/7-ssh-baksteen.png)

---

## Privilege Escalation & Root

After successful privilege escalation, we obtained a root shell:

![Root Shell](images/9-root-flag.png)

**Flag Captured!**

---

## Attack Summary

| Phase                  | Technique                      | Tool              |
|------------------------|--------------------------------|-------------------|
| Recon                  | Port Scanning                  | Nmap              |
| OSINT                  | GitHub + Twitter               | Browser           |
| Cracking               | MD5 Dictionary Attack          | John the Ripper   |
| Initial Access         | POP3 Exploitation              | Telnet            |
| Shell Access           | SSH Login                      | SSH               |
| Privilege Escalation   | Local Exploit                  | Bash              |

---

## Lessons Learned

- Exposed POP3 services are high-risk.
- MD5 passwords without salt are easily cracked.
- Leaking files on GitHub can lead to full compromise.

---

**Writeup by:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)
